---
layout: post
title: "Gist: AI Web Page Summary"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: gist-web-page-summary-cover.png
---

Continuing my exploration of AI tools, I created the **gist, a Safari Web Extension based on OpenAI GPT3**. It allows users to quickly get a summary of the active web page. My goal for it was not to create a commercial app but to explore the benefits of such system and learn some new technical skills.

<iframe width="615" height="328" src="https://www.youtube.com/embed/Lw6EWRhOvxw" frameborder="0" allowfullscreen></iframe>

Although the app works fine, I am not convinced that it's beneficial in the current version of the app and the AI used in it. Here are a few thoughts on this matter.

For any text summary to be really useful, it needs to be **factually correct** and **hit all the essential bits** of the story. There are several challenges embedded in that statement.

At the meta level, the AI summary is, at best, **the second derivative of the actual event (event -> web article -> summary)**. Meaning that its upper bound on correctness is the source article, and it will miss everything that the article misses in the first place. In the worst case, if the source article is false, the AI summary will be false as well. A possible way to mitigate this would be to let AI automatically try to scoop other articles on the same topic and then extract the summary or present opposing views if they exist.

By **"factually correct,"** I mean, in the practical context, that produced summary **does not misrepresent in any shape or form** what was written in the source article. Our current large language models are truly impressive statistical pattern matching machines and usually work as expected. But things can go wrong and will inevitably do so. Unfortunately, we don't have a good way to identify when the model is wrong, nor can we guarantee the performance on any random data we can encounter on the internet. Moreover, one can imagine **malicious actors embedding specific text structures** that would "confuse" the AI system or make it output particular text that the attacker wants. Adversarial attacks and examples exist in computer vision, and there is already research on adversarial attacks on large language models.

Finally, **what is important in a story is not an objective thing**. Yes, in most cases, there are a few key points to the story that we are interested in. Still, sometimes we might be looking for a specific piece of information that is more niche or of pronounced interest specifically to us. By providing additional instruction in the prompt, we could indicate to AI what is important to us. However, that would slow down the process and require manual intervention on the user's part.

On the technical level, there are a few issues that I left unresolved for now:

1. Getting the summary can take up to 10 seconds if the article is very long. Unfortunately, there is not much I can do about that since the slow part is on the OpenAI side.
2. AI parameters are hard-coded, and the user can't change them in the UI.
3. There is no proper handling/chunking of long texts, which can result in exceeding the prompt token limit.
4. Library used for web page text extraction is a hit or miss, depending on the page layout, which has a downstream effect on the AI summary quality.
5. The way the text extraction library is loaded is not optimal, and some websites block such an approach.
6. App is not thoroughly tested and likely contains bugs.

Neither of these limitations, except the first one, is hard to solve though. But I'll be shelving this project for the time being, so they will remain unresolved 🙂
