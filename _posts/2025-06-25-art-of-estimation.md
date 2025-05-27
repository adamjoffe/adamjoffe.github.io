---
title: "The Art of Estimation"
date: 2025-06-25 12:30:00 +0000
categories:
  - Software Engineering
tags:
  - planning
  - performance
  - prioritisation
  - reasoning
math: true
---

## Estimation of Meaning

Why bother spending the time to estimate anything? Why not just spend the effort working on the problem? As engineers, the primary purpose for making estimates is to help us reason and prioritise. It also provides quantitative data for processing, allow us to determine if a bottle neck is problematic or not.

## Estimation of Maths

## Estimation of Decision

When approaching any problem, it is critical you an correctly identify the right area to focus on in first and prioritise. As engineer's we often want to do everything and address all problems to make it perfect. However, we have finite time in life, so we must selectively apply our time. So let's go through a concrete example where estimation skills can correctly guide you through a system design problem. Let's say you are designing a *"top 5 currently most played"* feature for a music streaming app (think Spotify). We are given this starting metric:

* 10 million active users at any time, interacting with the app

To begin with, know we will need an API service that provides the list from the backend and a way to know what users are listening to what songs. So let's start estimating! We can start with a foundational rough estimate that each song is an average length of 3 min. From this we know that users will likely only interact with an app every 3 min, so the list API will need:

$$10,000,000 / 180s \approx 56,000\ req/s$$

Additionally, if we need to know a song start and end event then for each song we have:

$$10,000,000 / 180s \* 2 \approx 112,000\ events/s$$

Given events need to result in a data *"write"* operation and API request a *"read"* operation, the event handling should definitely be the primary concern! In this example, we used estimates to take a step back and use quantitative data points to determine a priority. The data points aren't concrete, but the difference in magnitudes of them is sufficient to give us the guidance we desired.

<!-- TODO: Heuristic user behaviour -->

## Estimation of Timing

<!-- TODO: performance vs. readability -->

*Notes:*

0. Finger in the air maths, cone of uncertainty
1. Rough equivalence (sin-theta = 1 for low angles)
2. Common incorrect choice due to bad estimation, performance vs. readability
3. Not just how to estimate but when to estimate. When weighing up a problem, recency bias or personal feelings easily cloud judgement of how important something it to work on. Stepping back and doing estimates helps create quantitative data points to help decide. > Heuristic behaviour patterns of users
4. Estimation of timing - estimating how long processes or things will take to determine magnitude of acceptable processing time vs. solving the performance bottleneck
