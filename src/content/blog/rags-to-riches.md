---
author: Adam Williams 
pubDatetime: 2024-01-16T06:03:44.203Z
modDatetime: 2024-01-16T06:03:44.203Z
title: From RAGs to Riches - Adding RAG to Loop Creation
slug: rags-to-riches 
featured: true
draft: false
tags:
  - docs
  - features
  - RAG 
  - pinecone 
description:
  Retrieval augmented generation makes the Loop Creator faster, better, stronger
---

### **tl;dr**

We now utilize existing Public Loops when creating new Loops.

### **What is RAG?**
Retrieval augmented generation, or RAG, is a technique for increasing the reliability and accuracy of large language models (LLMs) by including external information/data in the context of the LLM call.

### How does this help create Magic Loops?
Previously, all Loop generation was one-off. That is, each time a user creates a Loop, they work with the Loop Creator to make a new Loop from scratch. 

We're pretty happy with how well this works today, but we've had RAG on our roadmap for many months now. 

The idea is simple: once a user publishes (and makes public!) a Loop, we can then use that existing user-verified logic when creating new Loops. 

### Example

Let's start with a simple (and popular) example Loop description: 
> send me the top 5 stories on hackers news

### **Before RAG**

Previously, this request would frequently rely on a 3rd party API to grab Hacker News data:

![Magic Loops before adding RAG](/images/MagicLoopsPreRAG.png)

This may work, but isn't great. The 3rd party data may not be up-to-date, may go out of service, and generally shouldn't be trusted.

### **After RAG**

Now that we've implemented RAG, the Loop Creator finds an existing Loop that's similar, and correctly scrapes the page instead:

![Magic Loops after adding RAG](/images/MagicLoopsPostRAG.png)

Success! 🎉

### How does it work?

We start by indexing all of the Public Loops into a vector database; we're using [Pinecone](https://www.pinecone.io/). 

To index the Loops, we first need to get the vector embeddings for the Loop descriptions. To do this, we use [OpenAI's `text-embedding-ada-002`](https://platform.openai.com/docs/guides/embeddings/what-are-embeddings) model.

Once we have the vector embeddings, we send the Loop data to Pinecone. 

When a user creates a new Loop, we then compare the new description embedding with similar embeddings within Pinecone. 

For any matches (note: currently just the top match), we include the Loop details in the context of the Loop Creator's LLM calls. This helps the Loop Creator see how a similar Loop was implemented.

### How good is it? 

Great question! There's still a lot to be done and measured.

The initial implementation is about as simple as you can get. We actually created this feature [at a hackathon](https://partiful.com/e/AlntdLtxh9Jh1J6Pcsma), so although it works decently today, there are many tweaks we can make to improve the retrieval, improve the indexing, and improve the Loop Creator's grasp of the additional context.

The good news is, the more Loops that get created, the better the Loop Creator will become!

Curious to see RAG in action? [Create your first Loop today.](https://magicloops.dev?utm_source=blog&utm_medium=referral&utm_campaign=rags_to_riches)
