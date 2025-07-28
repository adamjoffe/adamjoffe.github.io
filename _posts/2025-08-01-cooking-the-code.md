---
title: Cooking the Code
date: 2025-08-01 12:30:00 +0000
categories:
  - Software Engineering
tags:
  - Coding
  - Architecture
  - Infrastructure
  - Fun
---

## A Favourite Analogy

Why *"Cooking the Code"*? Well these are two things I really enjoy, writing code and cooking. Cooking the code is not to be confused with *"Cooking the books"*, this is not something illegal just a fun analogy. In this shorter post I will go into some of the interesting parallels I see between cooking and software engineer, and also what cooking has taught me about how to approach software engineering.

![Cooking the Code](../assets/img/posts/2025-08-01-images/cooking-the-code.png)

## Baking: Code and Infrastructure

Writing in a programming language or configuring infrastructure is analogous to baking. Baking is precise and systematic. When following a recipe the amount of ingredients, order of operations, and techniques you use are extremely important to the outcome of the final product. For example, if you don't correctly layer butter into the pastry for croissants, or you don't keep the butter cold enough, they won't rise into perfect flakey cresents. The parallels should be clear here, when writing code, we must adhere very specifically to the [syntax](https://en.wikipedia.org/wiki/Syntax_\(programming_languages\)) and [semantics](https://en.wikipedia.org/wiki/Semantics_\(computer_science\)) of the language we're working with, otherwise it simply won't work. This is the same with configuring infrastructure, especially if we're using an [Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_code) service like [Terraform](https://developer.hashicorp.com/terraform). If we do anything incorrect, the configuration will be rejected and the lovely infrastructure cake will not rise.

Whilst sometimes a variance in the process or ingredients can yield a functional product, it will never be "right". This can be seen with the variance in the cookies below:

![Cookie Variance](../assets/img/posts/2025-08-01-images/cookie-variance.jpeg)

You will likely have a preference of how you like your cookies, which will vary person to person. However, ultimately the cookie you desire is specific and to achieve it the same ingredients and process must be followed each time without variation. Like writing software or standing up infrastructure, there is variance in the outcome but to reach the desired outcome, the same steps must always be followed exactly.

## Cooking: Architecture and Design

Unlike baking, when you are cooking there isn't always a set recipe you should follow. Cooking a dish is more freeform, you need to taste the dish as you go and determine what needs to be added to go in the direction that is right for your vision. With baking, the parameters you can tweak are very limited:

* If something needs hydration, you will add water
* If something needs richness, you will add egg or butter
* If something needs sweetness, you will add sugar

However, when it comes to cooking you often balance around the 5 basic flavour groups:

![5 Basic Flavours](../assets/img/posts/2025-08-01-images/5-basic-flavours.jpg)

Within each of these groups, there are a plethora of options to add to your dish to achieve a balance of these.

![Basic Flavours Ingredients](../assets/img/posts/2025-08-01-images/basic-flavours-ingredients.png)

When choosing an ingredient, you need to consider its more subtle flavour profiles as well witin these groups, and even details like the texture ingredients contribute too.

In my opinion, this is very similar to architecture and design. It is a signficantly more creative space that code and infrastruture. There is almost never one "right" answer, and you need to know the right tools to grab for when balancing pros and cons to reach your vision. Just like cooking as well, sometimes you add too much of a wrong ingredient, things go wrong and you need to start over. Not every dish is going to come out good, but you can take learnings from the failure to improve what you cook up next time!
