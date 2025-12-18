---
layout: post
title: "Mastering UX in Power Apps: Building a Dynamic Character Limit Counter"
date: 2025-12-18
categories: [PowerApps, UX, Tutorial]
tags: [Canvas App, Low-code, Design]
description: "Learn how to improve User Experience by adding a dynamic character counter linked directly to your Data Source."
---

As Power Apps developers, we often focus heavily on logic and data integrity, but User Experience (UX) is what separates a functional app from a great app.

One small but powerful UI element that dramatically improves usability is the Character Limit Indicator.

## Why is this crucial for UX?

This simple counter plays a vital role in Jakob Nielsen’s Usability Heuristics, specifically regarding the Visibility of System Status.

> Users should never have to guess how much content they can type into a field. By providing a counter (e.g., "0/255"), you offer immediate feedback. This prevents frustration by letting the user know their limits before they hit the save button and trigger a validation error.

![Character Limit Indicator Example]({{ site.baseurl }}/assets/img//2025-12-18-Mastering-UX-in-Power-Apps-Building-a-Dynamic-Character-Limit-Counter/Animation.gif)<br> *Figure 1: Screenshot of the text input with the 0/255 counter visible*

---

## How to Implement It

Adding this to your Canvas App is straightforward. Here is the step-by-step guide to making it dynamic and maintenance-free.

Prerequisite: Enable Modern Controls This guide uses the Modern Text Input control. While these are becoming the standard, they might not be enabled by default in your environment or older apps.

Before you begin, ensure you have access to them:

Go to Settings > Updates.

Search for "Modern controls and themes".

Ensure the toggle is set to On.

Note: If you are using Classic Controls, the logic remains similar, but you will use .Text instead of .Value and the DelayOutput property set to false instead of TriggerOutput.

### 1. Add the Label
First, place a standard Text Label control immediately below your Text Input control.

### 2. The Formula
Instead of hardcoding a number (like "255"), we want to fetch the limit directly from the Data Source (e.g., SharePoint). This ensures that if you change the column limit in SharePoint later, your app updates automatically without you having to rewrite code.

Set the Text property of your new label to the following formula:

`Len(inp_NewName.Value)  & "/" &  DataSourceInfo([@'Example SharePoint list'], DataSourceInfo.MaxLength, YourColumnName)`

**Let’s break down the variables:**

| Variable | Description |
| :--- | :--- |
| inp_NewName | This is the name of your Text Input control. |
| 'Example SharePoint List' | The name of your connected SharePoint list. |
| "YourColumnName" | The internal name of the specific column in that list. |

### 3. Enforce the Limit (The Input Control)
Don't just *show* the limit—*enforce* it! To physically prevent users from typing more characters than the database allows, you should apply the same logic to the input box itself.

Select your **Text Input** control, find the `MaxLength` property, and set it to:<br>
`DataSourceInfo([@'Example SharePoint list'], DataSourceInfo.MaxLength, YourColumnName)`

### 4. The "Gotcha": Updating in Real-Time
By default, Power Apps might not update the character count until the user clicks out of the box. To make the counter update while the user is typing, you need to change a specific setting on the Text Input control.

Find the **TriggerOutput** property. This property determines when the control updates its **Value** and triggers OnChange. Set it to **Keypress**.

Here is how the options work:

* **Delayed** - Update the control's value when the user pauses typing.
* **FocusOut** - Update the control's value when the user selects a different control or clicks outside the control.
* **Keypress** - Update the control's value immediately on every character input. (Select this one!)

---

## Why use DataSourceInfo?

Using the DataSourceInfo function is a pro-tip for scalable development. It allows you to validate user input using column-level information defined in your database.

* **Dynamic MaxLength:** As shown above, DataSourceInfo.MaxLength ensures your UI always matches your database schema.
* **Dynamic Required Fields:** You can also use DataSourceInfo.Required to check if a field is mandatory, allowing you to show/hide asterisks (*) or error messages dynamically.

You can read the full documentation on this powerful function here:
[Microsoft Learn: DataSourceInfo function](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-datasourceinfo)
