---
author: Adam Williams
pubDatetime: 2024-01-25T09:00:00-08:00
modDatetime: 2024-01-25T09:00:00-08:00
title: Improving validation for the Loop Creator
slug: enhanced-validation
featured: true
draft: false
tags:
  - updates
  - validation
  - loop creator
description: Introducing new enhancements to Loop Creator validation, enabling greater control and flexibility in automating your workflows.
---

## **tl;dr**

> Validation just got easier 🎉 -- we've made the Loop Creator more intuitive and error-tolerant

## **Before**

In many cases, the Loop Creator was... a pain to work with.

It would attempt to validate and rewrite a Block (up to 3 times), even if the Block's output was already correct or irreparable.

## **Now**

### Instant Feedback

To streamline the Loop building process, we've upgraded the Validate functionality to provide immediate feedback on each block:

- **Success**: "Block looks good."
- **Fail**: "Block output appears incorrect!"

Here's what success looks like:

![Block looks OK placeholder](/images/block-looks-good.png)

And here's what a potential failure looks like:

![Block output appears incorrect placeholder](/images/block-appears-incorrect.png)

### **Overruling False Validation**

When a Block fails validation, you can now exercise more authority:

- If you're confident the Block's output is fine, override the decision and proceed with: **Correct** _(Block is actually good, continue!)_
- If the output is **Incorrect**, you now have the power to revise the description directly, giving you finer control over the automatic fixes to your Loop.

Here's what revising a Block's description looks like:

![Rewrite block with new description placeholder](/images/block-rewrite-ui.png)

## Other changes

This update includes a few other fixes as well:

#### **Streamlined JSON Mode**

Function calling is out; enter pure JSON mode. This change means the Loop Creator (LC) can focus on one block at a time, enhancing stability and predictability.

> We should probably dedicate a whole post to why we moved away from Function Calling to JSON mode... another time!

#### **Revamped Validate Prompt**

We've rewritten the validate prompt to be more transparent and actionable. This means clearer communication, reducing development time and friction.

#### **Launching "Request Variable" in LC**

We've had this functionality feature-flagged for awhile, but are excited to share it with y'all!

The Loop Creator can now "Request Variables" as part of it's validation step, helping alleviate situations where an email, API key, or other required variable is needed for the Block to work.

Here's what it looks like:

![Request Variable from user](/images/loop-creator-request-variable.png)

#### **Improved Error Handling**

We've tidied up loose ends in error handling within the Loop Creator, aiming to make the Loop creation as smooth as sailing.

> **As smooth as sailing** -- thanks ChatGPT...

## **Wrap-Up**

These enhancements are a big step forward in giving you the autonomy and tools to build more complex, error-free Loops faster than ever. We're committed to improving the Loop Creator experience, and we welcome [your feedback](mailto:humans@magicloops.dev) on these updates.

> Start exploring these new features now and take your Loop generation to the next level!

[Create a Loop with new validation controls today](https://magicloops.dev)
