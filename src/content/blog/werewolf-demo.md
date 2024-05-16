---
author: Chinat Yu
pubDatetime: 2024-05-12T01:14:22-08:00
modDatetime: 2024-05-12T01:14:22-08:00
title: Automating Werewolf Assignments with Magic Loops
slug: automating-werewolf-assignments
featured: true
draft: false
tags:
  - automation
  - games
  - email
  - gpt-4
description: Streamlining role assignments in the game of Werewolf using Magic Loops and Sheety API
---

# Video Walkthrough

https://youtu.be/pch2MP-g0dM

# Step 1: Open up the sidebar

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/90d3c100-6729-4fbe-96f1-0f43a728de1f/Untitled.png)

# Step 2: Create a Manual Loop

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/a08290c4-c789-4236-9da3-324b804f5b81/Untitled.png)

# Step 3: Customize the title and description for your loop

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/1267555b-baaa-4fab-afd8-3f907cfe77ed/Untitled.png)

# Step 4: Change the `Trigger` to be `Email`

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/69543f67-35f5-44f5-8371-ef3556d68746/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/6cdcc77d-06f3-49c2-bae5-28c15bd9c1cc/Untitled.png)

# Step 5: Send a sample email to the provided email address to create a sample input

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/402cf3a2-46ae-4d21-be6b-03f9a050c95e/Untitled.png)

# Step 6: Add a `Code` block to print out the email

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/f1c21f42-5f68-4809-ae84-53e0c3670686/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/c4e0b036-53a4-4185-8999-ebf5e6107072/acdebbcc-418d-42ef-823a-179cae3d886b/Untitled.png)

# Step 7: Set up the API endpoint at `Sheety`

<aside>
💡 Refer directly to [Sheety documentation](https://v2.sheety.co/docs/getting-started) regarding the set up, but you should make sure that you have the API endpoint, and also the `GET` and `PUT` requests activated.
</aside>

[Sheety](https://dashboard.sheety.co/)

<aside>
💡 This is the spreadsheet that I used: [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1YqLBhDzaFf4JjKVX6xyEupO_yUNuuvojFi1quraeQas/edit?usp=sharing)
</aside>

# Step 8: Set up the code block to access the `Sheety` API endpoint

<aside>
💡 This is the prompt that I use. Note that you might need to tweak the prompt based on your use case, and may need a few tries in order to get the API access to work properly.
</aside>



Building software that builds software is no easy task, but with the right data in place, we can now increase the capabilities of Magic Loops for everyone.

What are you waiting for? [Create your first Magic Loop today!](https://magicloops.dev)
