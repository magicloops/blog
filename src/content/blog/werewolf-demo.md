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

Hi everyone! Today, I'd like to introduce you to Magic Loops and demonstrate how to use it to build a game of Werewolf. Werewolf is a social deduction game where villagers try to identify and eliminate the werewolves before they overrun the village.

Using Magic Loops, we can automate the role assignment process, which is usually manual and time-consuming. Here's a brief overview:

1. **Set Up a Google Spreadsheet**: Create a spreadsheet to list roles and players.
2. **Create a Magic Loop**: Title it "Werewolf" and set a trigger, like an email trigger.
3. **Send an Email**: Use the email trigger to send a request for a role assignment.
4. **Extract Data**: Use Magic Loops to access the spreadsheet, identify unassigned roles, and assign a role randomly.
5. **API Integration**: Use the Sheety API to interact with Google Spreadsheets.
6. **Generate and Execute Code**: Use JavaScript to automate the role assignment.
7. **Send Email Response**: Customize and send the assigned role back to the user via email.

This process simplifies the game setup and ensures fair and random role distribution. I hope you find this tutorial helpful and look forward to your feedback. Thank you!

# Video Walkthrough

[![Werewolf Tutorial](https://i9.ytimg.com/vi/QwMxe-ed-pg/mq1.jpg?sqp=COyk-rIG-oaymwEmCMACELQB8quKqQMa8AEB-AH-CYAC0AWKAgwIABABGGUgYChXMA8=&rs=AOn4CLAtHbeoIod2SxYZzkS4oULUhCa0Xg)](https://youtu.be/QwMxe-ed-pg "Werewolf Tutorial")

# Step 1: Open up the sidebar

![Untitled](/images/werewolf_demo_photos/werewolf_1.png)

# Step 2: Create a Manual Loop

![Untitled](/images/werewolf_demo_photos/werewolf_2.png)

# Step 3: Customize the title and description for your loop

![Untitled](/images/werewolf_demo_photos/werewolf_3.png)

# Step 4: Change the `Trigger` to be `Email`

![Untitled](/images/werewolf_demo_photos/werewolf_4.png)

# Step 5: Send a sample email to the provided email address to create a sample input

![Untitled](/images/werewolf_demo_photos/werewolf_5.png)

# Step 6: Add a `Code` block to print out the email

![Untitled](/images/werewolf_demo_photos/werewolf_6.png)

![Untitled](/images/werewolf_demo_photos/werewolf_7.png)

# Step 7: Set up the API endpoint at `Sheety`

<!-- <aside> -->

💡 Refer directly to [Sheety documentation](https://v2.sheety.co/docs/getting-started) regarding the set up, but you should make sure that you have the API endpoint, and also the `GET` and `PUT` requests activated.

<!-- </aside> -->

[Sheety Platform](https://dashboard.sheety.co/)

<!-- <aside> -->

💡 This is the spreadsheet that I used: [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1YqLBhDzaFf4JjKVX6xyEupO_yUNuuvojFi1quraeQas/edit?usp=sharing)

<!-- </aside> -->

# Step 8: Set up the code block to access the `Sheety` API endpoint

<aside>
💡 This is the prompt that I use. Note that you might need to tweak the prompt based on your use case, and may need a few tries in order to get the API access to work properly.
</aside>

```
Access the Google Spreadsheets via Sheety API, identify the roles that have yet been assigned, randomly assign the user to a role, and then update the Google Sheets leave with assigned with true, return the role, description, and assigned variables

https://api.sheety.co/[REPLACE WITH YOUR OWN]
```

![Untitled](/images/werewolf_demo_photos/werewolf_8.png)

<aside>
💡 Check the `Google Sheets` to make sure that it is updated correctly.
</aside>

# Step 9: Add a custom LLM block to create a response message back to the player

![Untitled](/images/werewolf_demo_photos/werewolf_9.png)

# Step 10: Add a `Send Email` block that returns the custom message to the user

![Untitled](/images/werewolf_demo_photos/werewolf_10.png)

# Step 11: Activate it and enjoy a game of Werewolf with your friends!

<aside>
💡 Make sure to check the spreadsheet to ensure that it is updated!

</aside>

Building software that builds software is no easy task, but with the right data in place, we can now increase the capabilities of Magic Loops for everyone.

What are you waiting for? [Create your first Magic Loop today!](https://magicloops.dev)
