---
layout: post
title: "Discord Bot for Notion"
author: "Marko Simic"
categories: journal
tags: [documentation,code]
image: discord-bot-for-notion.png
---

## Introduction

I recently began collaborating with a friend on a small project, and we decided to use Discord for communication and Notion for work organization. This combination works well, but we also wanted a simple notification system in Discord when our Notion database gets updated. However, Notion does not have a Discord integration (e.g., Discord bot), or I just didn&rsquo;t find one, so I decided to quickly code one.

Discord offers [discord.py](https://discordpy.readthedocs.io/en/latest/), an easy-to-use API wrapper implemented in Python, which we can use to code our Notion bot. On the other hand, we can use an unofficial Python library [notion-sdk-py](https://github.com/ramnes/notion-sdk-py) that implements the official [Notion API](https://developers.notion.com/reference/intro). It is not necessary to use this particular library, as we could achieve the same functionality by calling the Notion API directly via the [requests](https://requests.readthedocs.io/en/latest/) library. However, the library does offer some additional conveniences.


## Coding the Bot

The goal of our Discord bot is to periodically check a specified Notion database for updates and post in a dedicated channel if there are any updates in that database. The database we are interested in tracking is the one we use for tasks.

The complete code is available on [GitHub](https://github.com/simicvm/discord-bot-notion), with the main logic contained in only four functions, so let&rsquo;s examine each one of them.

```python
async def get_notion_pages() -> List[dict]:
    """
    Fetch pages from the Notion database since the last checked timestamp.

    :return: A list of pages.
    """
    global last_checked
    try:
        pages = notion.databases.query(
            **{
                "database_id": DATABASE_ID,
                "filter": {
                    "and": [
                        {
                            "timestamp": "last_edited_time",
                            "last_edited_time": {"after": last_checked},
                        }
                    ]
                },
            }
        ).get("results")
        last_checked = datetime.utcnow().replace(microsecond=0).isoformat()
        logger.info(f"Last checked at: {last_checked}")
        logger.debug(pages)
        return pages
    except Exception as e:
        logger.error(f"Error fetching pages from Notion: {e}")
        return []
```

This function polls the Notion database for updates. The Notion API allows us to filter our database queries, and we use the `last_edited_time` property to check if an item was edited since our last check. If you have a team distributed across multiple time zones, you must ensure that Notion and your code use the same time zone. If you have other specific filter requirements, this would be the place to add them.

```python
def format_page_message(page: dict) -> str:
    """
    Format the page title to be sent as a Discord message.

    :param page: The Notion page.
    :return: The formatted message.
    """
    title = page["properties"]["Name"]["title"][0]["text"]["content"]
    message = f"**New Update:** {title}\n"
    return message
```

The Notion API returns a list of dictionaries we need to parse for the necessary information. We only want the name of the task that was updated, but you can easily choose other properties as well.

```python
async def poll_notion_database() -> None:
    """
    Poll the Notion database and send updates to a Discord channel.
    """
    while True:
        pages = await get_notion_pages()
        channel = bot.get_channel(DISCORD_CHANNEL_ID)
        for page in pages:
            message = format_page_message(page)
            try:
                await channel.send(message)
            except Exception as e:
                logger.error(f"Error sending message to Discord: {e}")
        await asyncio.sleep(120)  # Poll every N seconds
```

This is the main loop that polls the Notion database and posts messages to Discord. Unfortunately, the public Notion API does not support webhooks (yet), so we need to poll it manually at predefined intervals. Another quirk is that the Notion database rounds time to a minute for `last_edited_time` and `created_time` properties ([source](https://developers.notion.com/changelog/last-edited-time-is-now-rounded-to-the-nearest-minute)), so the loop has to be at least 2 minutes long for our filter to work correclty. We want daily updates, so the risk of `last_edited_time` being equal to `last_checked` is minimal. However, if you plan on polling Notion more frequently, you should devise a better scheme to avoid potential collisions.

```python
@bot.event
async def on_ready() -> None:
    """
    Event that occurs when the bot is ready.
    """
    logger.info(f"{bot.user} is now online!")
    try:
        await poll_notion_database()
    except Exception as e:
        logger.error(f"Error polling Notion database: {e}")
```

Here, we dispatch the main loop. We use an `event` decorator to register the event to listen to. More specifically, we listen for `on_ready`, which is called when the Client (Bot) is done preparing and is logged into Discord.


## Integrating the Bot

Now that we have the code, there are a few more things that we need to do before the bot becomes operational.


### Create a Notion Integration

Go to <https://developers.notion.com> and click `View my integrations` (or go directly to <https://www.notion.so/my-integrations>).

Create a `New integration`.

Give it any name you like, choose the desired workspace to associate with, and optionally add a logo.

Write down the `Internal Integration Token` in the `Secrets` section for later use.

In `Capabilities`, select the desired capabilities for the integration. For this bot, they should be: `Read content` and `No user information`.


### Create a Discord Bot

Open the Discord developer portal at <https://discord.com/developers/applications>.

Create a `New Application`.

Optionally fill in the `DESCRIPTION` and `TAGS`.

In the `Bot` settings, click `Reset Token` and write it down for later use.

In `OAuth2` -> `URL Generator`, select `bot` in `SCOPES` and `Send Messages` in `BOT PERMISSIONS`.

Open the `GENERATED URL` in a new browser window.

Select the server to add your new application to.

Follow the rest of the steps, and you should see a message in the `general` channel of your Discord server informing you that the application has been added.


### Set Up Tokens

In the root of the project directory, create an `.env` file with the following fields:

    DISCORD_BOT_TOKEN = ''
    NOTION_API_KEY = ''
    DATABASE_ID = ''
    DISCORD_CHANNEL_ID = ''

Right click on the Discord channel where you want the bot to post updates and select `Copy Channel ID`. Paste that ID into `DISCORD_CHANNEL_ID`, e.g., `DISCORD_CHANNEL_ID = '1171832436840643745'`.

Paste the Notion Integration Token into `NOTION_API_KEY`.

Copy the Notion database ID you want to track and add your integration to the database. Check this [answer](https://stackoverflow.com/questions/67728038/where-to-find-database-id-for-my-database-in-notion) on how to do that. Paste the obtained ID into `DATABASE_ID`.

Paste the Discord bot token you obtained earlier into `DISCORD_BOT_TOKEN`.

Optionally, add the poll interval in seconds, e.g., `POLL_INTERVAL = 120`. The interval should be at least 120 seconds, and it defaults to that value if not provided.

Optionally, set the log level, e.g., `LOGLEVEL = 'INFO'` . Allowed values are: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`. The default value is INFO.


### Give Channel Permission (optional)

If your desired channel is private, you will need to give permissions to the bot. Go to `Edit Channel` -> `Permissions` in Discord for the channel you want the bot to post in and make the appropriate changes.


## Run the Bot

Launching the bot is straightforward – just type `python discord_bot.py` in your command line within the project folder. Remember, though, the bot operates only while the script runs. So, if you&rsquo;re aiming for round-the-clock bot action, you&rsquo;ll need a dedicated server that&rsquo;s constantly online.


## Conclusion

In this blog post, we have walked through the process of creating a basic Discord bot that polls a Notion database for updates and posts a message in a dedicated channel when there are new updates. The bot serves as a simple but functional integration between Discord and Notion.

While the described bot is a basic implementation, there is always room for improvement. Some potential enhancements could include better error handling to make the bot more resilient to unexpected issues, increased modularity to allow for easier updates and code maintenance, and the addition of more functionality such as notifying users of upcoming deadlines or allowing them to interact with the Notion database directly through Discord commands.

Overall, this Discord bot demonstrates how you can leverage existing libraries and APIs to create a custom solution for your team&rsquo;s needs. With a bit of creativity and development, you can extend and adapt the bot to make your collaboration experience even more seamless and efficient.

