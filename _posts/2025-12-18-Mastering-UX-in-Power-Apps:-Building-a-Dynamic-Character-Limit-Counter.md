---
layout: post
title: "Mastering UX in Power Apps: Building a Dynamic Character Limit Counter"
date: 2023-10-29
categories: [Power Apps, UX, Tutorial]
tags: [Canvas App, Low-code, Design]
description: "Learn how to improve User Experience by adding a dynamic character counter linked directly to your Data Source."
---

As Power Apps developers, we often focus heavily on logic and data integrity, but **User Experience (UX)** is what separates a *functional* app from a *great* app.

One small but powerful UI element that dramatically improves usability is the **Character Limit Indicator**.

## Why is this crucial for UX?

This simple counter plays a vital role in **Jakob Nielsen’s Usability Heuristics**, specifically regarding the **Visibility of System Status**.

Users should never have to guess how much content they can type into a field. By providing a counter (e.g., "0/255"), you offer immediate feedback. This prevents frustration by letting the user know their limits *before* they hit the save button and trigger a validation error.

![Character Limit Indicator Example](/assets/img/1.png)
*Figure 1: Screenshot of the text input with the 0/255 counter visible*

---

## How to Implement It

Adding this to your Canvas App is straightforward. Here is the step-by-step guide to making it dynamic and maintenance-free.

### 1. Add the Label

First, place a standard **Text Label** control immediately below your Text Input control.

### 2. The Formula

Instead of hardcoding a number (like "255"), we want to fetch the limit directly from the Data Source (e.g., SharePoint). This ensures that if you change the column limit in SharePoint later, your app updates automatically without you having to rewrite code.

Set the `Text` property of your new label to the following formula:
