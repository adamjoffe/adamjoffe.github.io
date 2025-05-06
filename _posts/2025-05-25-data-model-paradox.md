---
title: "Data Model Paradox"
date: 2025-05-25 12:30:00 +0000
categories:
  - Software Engineering
tags:
  - architecture
  - data
  - domain
---

## Data at the Root

At the heart of every project and every product is data. Data is what gives value and meaning to a piece of software. Lets imagine you have constructed an infinitely horizontal scaling [microservice platform](https://microservices.io/), deployed smoothly with [blue-green deployment phases](https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/welcome.html) and automated smoke testing. However, the data model underlying everything is just a single text file that each service must acquire a lock for before reading from and writing to. This entire thing is now completely useless. It doesn't matter how sleek and optimised the service is, if the data is slow, it all falls over.

This might seem like an absurd example, because it is, but if you don't get the data modelling part right, it will feel similar. "Independent" microservices with poorly isolated data domains will need to constantly talk to one another. This creates strong coupling and a fragile microservice platform where any slight API or behaviour change will cause a failure that ripples across the services.

![Data Modelling Overload](../assets/img/posts/2025-05-25-images/data-modelling-overload.png)

Getting the data model right should be the most critical part of any project or product, this is compounded by the fact that it is also the hardest part to change: DB migrations, data [ETL](https://en.wikipedia.org/wiki/Extract,_transform,_load) from legacy systems, data model constraint backwards compatibility. To be able to get it right, you need extensive knowledge of the domain and use cases. Often this knowledge requires years of experience in a particular domain to fully understand all of it. However, if you're working in a greenfield space or even just wanting to skill up in a new space, then we need a strategy to progress without shooting ourselves in the foot for the future.

## Will I Need this?

Like all things, evolving our data model in small iterations and validating what we've done in the real world with real life customers is going to give us the best results. Therefore, when you're making any change to a data model or its relationships don't try to "plan for the future". If you aren't using a data point or a relationship immediately when created, then it isn't needed and don't use it, [YAGNI](https://martinfowler.com/bliki/Yagni.html). If you're not using something, it isn't being validated in production and that is simply a liability. If you really need it, then it is guaranteed the next step in your iteration will just add it anyway.

Saying never adding something else it is used can seem like a harsh line to draw. So as a caveat there are some legitimate, edge cases, where adding a data point that isn't being used is acceptable. This is often when the data point must exist from day zero for tracking or prosperity reasons. The most common example of this is when the data point is used for regulatory or reporting purposes. In these cases, there is almost always an internal or external domain expert involved that provide validation of this data point.

Finally, if you really are on the fence about adding something, just remember it is easier to add something than remove it. Adding is a "create" operation which by nature means there is no dependency or business logic hanging off the data point. Whilst removing more easily introduces bugs or breaking changes in the current behaviour. The other thing to consider is looking at the data constraint and integrity view, you want to ensure each data point is as strictly constrained as possible. It is always easier going from more constrained to less constrained. If you make the data point too early, before it is fully utilised, it will gather "legacy" values. Then when it is finally used and validated in product, we will often find that there was a missing constraint! Uh-oh! We already have legacy values that need to be investigated and migrated when we never needed this headache.

## When to Migrate

Just because ever bit of data is being used, doesn't mean it is guaranteed to be right. As is the nature of the beast, there will always require changes and shifts from where we thought we needed to go, to where we now think we need to go. As such, migrating will be an inevitable part of almost ever data models life.

## Hindsight 20:20

*Notes:*
Data model paradox
0\. Intro - Data model is the hardest to change, so you want to make sure it's right. To get it right you need to know more about the domain or use case. The know more about the domain or use case you need to try things out. The try things out you need to iterate and improve a solution. To start building a solution you need a data model...

1. Will I needs this? - don't add things because you think you'll need it in the future. Adding easy, removing harder
2. When to migrate - how to know when things need to change a bit
3. Hindsight 20:20 - when to rebuild the model entirely and transform (duplication "shadow mode")
