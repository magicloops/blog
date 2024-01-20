---
author: Adam Williams
pubDatetime: 2024-01-20T01:14:27-08:00
modDatetime: 2024-01-20T01:14:27-08:00
title: Why we're building Magic Loops
slug: why-were-building-magic-loops
featured: true
draft: false
tags:
  - founding story
  - what is a magic loop
  - our journey
description: What led us to build Magic Loops and what we're excited about next
---

## **tl;dr**

> Our goal is to 10x the number of programmers on Earth 🌍

## Background

We started building an AI “agent” with the goal of empowering individual contributors (ICs).

The idea was simple:

- Many tasks in an IC’s role are repetitive
  - Automating communication (CSMs)
  - Capturing product requests (AEs)
  - Onboarding customers (Sales Engineers)
  - Updating SaaS tools
  - Managing schedules

Our initial hypothesis was to build a product using large language models (LLMs) that allowed these IC’s to automate the data entry and other mundane tasks in their day-to-day work.

The tool resembled a ChatGPT-like UX, but built for teams (shareable, multi-user chat, PII redaction, RAG data retrieval w/Notion, the works).

The MVP idea was simple, figure out how people use LLMs and then automate that usage; essentially our goal was to understand communication patterns and repetitive tasks (e.g. format this data differently, extract client name/email/address, summarize conversation, etc.).

We launched. Success 🎉

## The Problem

We grew to 25 companies (“customers”) on the platform and were accepted to Y Combinator. 🎉🎉

> Candidly, we were fortunate to have been in industry for so long, as it was relatively painless to get people who trust us to try our product.

But the data wasn’t great.

User interviews pointed to gaps in the tool: “can it pull from Gong?”

Usage was sporadic; people were just figuring out how to use ChatGPT.

We launched to organizations of all sizes, from 3 person startups to 300+ person professional firms.

One common denominator: they all had software engineers.

Analyzing the usage patterns led to a few key insights:

1. Code blocks were very common
2. Non-engineer users struggled to find usage in their day job\*
3. We were missing every integration imaginable

> - Some due to trust issues, but most still found GPT-4 useful for one-off tasks (make communication professional, what happened on this day in history?, names for my new cat).

This led to a few “micro-pivots” of the product.

## Pivot Hell

We first started by building integrations for the top use-cases (Slack, Notion, generic RAG, file upload, scraping, etc.).

Usage was minimal.

**Our Slack integration was installed twice and used just once.**

From here, we dove towards developers.

Deeper analysis pointed out that 95% of recurring usage came from developers.

Although we had hundreds of weekly active users (WAUs), developers were the only ones coming back.

We found our ideal user: developers who use the site multiple times per week.

Of our ~100 DAUs, 25 of them were developers coming back 7x a week.

We had a sticky product.

Or… **we were just GPT-4 resellers.**

## Back to the drawing board

Although we had a product that users loved, it wasn’t _our_ product.

We had finally come to the conclusion that, in the short-term, LLMs are primarily useful for three main tasks\*:

1. Education\*\*
2. Code generation
3. Transforming data

> - \*Yes, there are many consumer use cases like role-playing chatbots, but we were narrowing to professional value.

> - \*\*And yes, education seems too difficult, my wife would be much better suited for that endeavor!

Given our previous user feedback, we knew there were 100s of valuable integrations that would be supercharged with LLMs.

We threw our top user requests up on a whiteboard:

![Bad handwriting](/images/magic-loops-whiteboard.jpg)

The obvious next step: let’s build an automation for each user and see what sticks.

After building 3 and struggling with the Nth low-code platform on the 5th, we realized something 💡

Taking a step back from the board, it became clear.

We were using LLMs to write the integration code, and primarily just validating that it works.

What if we built a code platform (or “cloud”) for the LLM generated code to run on?

Why deal with servers if all you care about is business logic?

**Why write business logic with curly braces if you can use plain English?**

## Magic Loops were born

We started with a quick prototype.

Let’s do single-shot code generation based on a user request.

The code will have access to first class functions (triggers, notifications, etc.), but will be entirely self-contained.

We prototyped the prompts in our previous product.

> Let’s add a Jupyter-style notebook interface to make it easy to understand and debug.

> Let’s show people?

## Hacker News: Hug of Love ❤️

We posted Magic Loops to Hacker News on August 1st, 2023. We hit the front page and stayed there all day.

_It was terrifying._

But we stayed up; mostly. There were a few (_read: many_) OpenAI rate-limiting errors in our logs.

> In hindsight, we should have thought through LLM load-balancing more seriously, but at least the traffic-serving autoscaling worked as expected.

Over the next month users created 20,000 loops.

Development stalled. When people are using your tool, it’s easy to get distracted by their insights for too long.

More importantly, you’re in the mindset that you don’t want your product to break more than it already is.

We pushed changes, of course, but we were much more deliberate than we needed to be.

**Popularity stagnates.**

## What were people using Magic Loops for?

Most of the early usage fell into 3 main buckets:

- ChatGPT automations
- Zapier-like integrations
- IFTTT style trigger/events

This was neat, but we knew our tool was capable of so much more.

After interviewing users we determined that, counterintuitively, developers were our loudest supporters.

It turns out that a natural language coding tool isn’t just for non-programmers.

> Our North Star is still enabling the next 10x programmers on Earth, but starting with developers will make the overall platform [better](https://blog.magicloops.dev/posts/rags-to-riches).

## Where are we now?

It’s been half a year since we launched, and usage is steadily increasing.

![90 days of Loop Growth](/images/90-days-of-loop-growth.png)

We’ve improved the product substantially, but we’re just now getting back into the rhythm of the pre-user days.

You can now use Magic Loops for a variety of interesting engineering tasks:

- **Custom APIs**
  - We support full REST (GET/POST/etc.)
- **GPT development**
  - Simply build a Loop for each of your GPT’s actions
- **LLM-enabled user flows**
  - Add AI to your product, with no need for a server or LLM API token
- **System-to-system integrations**
  - Multi-step workflows are easy out of the box
- **Background tasks**
  - Why schedule a CRON ever again?
- **Discord Bots**
  - Here's an [example Haiku Bot](https://magicloops.dev/loop/534dff72-7582-402f-8c9e-8e78c4cb901b)

## The Product

Magic Loops can be thought of as a combination of AWS Lambdas and a Jupyter Notebook, with a bit of LLM magic sprinkled in.

> We use LLMs both to help you create Loops, and as powerful tools within the Loops themselves.

We’ve recently added a “Loop Creator” that utilizes a multi-shot+[RAG approach](https://blog.magicloops.dev/posts/rags-to-riches) to better facilitate Loop creation on your behalf.

You can now have an iterative conversation before creating your Loop.

You can also benefit from the creations of others, as we now reference relevant [Public Loops](https://magicloops.dev/#public-loops) to help build the correct Loop the first time.

## Where we’re going

Magic Loops are incredibly powerful already, but they will get better.

We want to enable the ability to use a local runtime for Magic Loop execution. To facilitate this, we plan to open-source the core Magic Loops components to allow anyone to run Loops locally.

We also want to go further.

Our vision for Magic Loops isn’t just simple system-to-system integrations, it’s to provide powerful programming abilities to anyone who has something to build.

People want interfaces, they want repeatability, they want state.

To best facilitate this, we’re expanding beyond pure data-driven flows and moving into the realm of databases and UI.

If working on the future of programming is of interest to you, we’d love to chat. Please reach out: founders@magicloops.dev

## Getting started

Our journey is far from over, but we’d love for you to give [Magic Loops](https://magicloops.dev) a try.

> We’d love it even more if you find a bug 🐛 and [report it](humans@magicloops.dev)!

**To the next 25 million programmers, godspeed 🥂**
