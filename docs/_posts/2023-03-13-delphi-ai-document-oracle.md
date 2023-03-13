---
layout: post
title: "Delphi AI: app for document Q&A and information retrieval"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: 
---

Large language models are poised to radically improve how we retrieve information and get relevant answers from our documents and databases.

I created a demo app to showcase the potential. Using only your natural language, you can do the following:

1. Q&A: get answers to your document-specific questions.
2. Information retrieval: retrieve files and metadata from the database.

The app uses OpenAI API for AI tasks and Weaviate for a vector database.

While answering questions is impressive, the real power of the system lies in its retrieval mode. When a user enters a search query, the AI converts their natural language request into a GraphQL API request that is sent to the database for classical search and filtering.

However, AI has limited knowledge of Weaviate, and by default, it cannot generate entirely valid API requests based on user input. To overcome that issue, we can provide Weaviate API documentation as a context for every user query. Using that context, AI can then successfully convert natural language queries into correct GraphQL queries and execute the database search.

If database search does not sound that impressive to you, keep in mind that virtually every software and service has APIs for interaction with them. So by using this in-context learning method, we can enable AI to interact with all of them. And in doing that, we are, in a way, teaching AI how to use tools.

Fun side note: I used ChatGPT to generate the script for narration in the video and ElevenLabs to generate the voice in it.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Q4oUV-oRvNA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
