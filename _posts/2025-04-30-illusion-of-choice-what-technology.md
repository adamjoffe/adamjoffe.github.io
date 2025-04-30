---
title: "Illusion of choice: What technology to use?"
date: 2025-04-30 09:00:00 +0000
categories:
  - Product Engineering
  - Software Engineering
tags:
  - product
  - architecture
---

## Where to Begin

When starting a new project, building a new product or enhancing something that already exists it is important to pick how we are going to solve the problem in front of us. Often as software engineers, we think the first question to answer is what technologies, frameworks or programming languages we would like to use. But is this really the right question to answer?

<!-- Picture of questioning tech choices -->
![]() 

## Inverted Problem

People are selfish. It isn't really their fault, that's just often the nature of being human. What we are interested in are tainted by our own experiences, since this is the only [primary source](https://en.wikipedia.org/wiki/Primary_source) we have to rely on. As such, we think the first problem to be solved is how we will build the solution. However, in reality this should be the last problem to solve, so we must invert our understanding of the problems.

The order of the problems we need to solve should align with how the project or product derives success. Success of this depends primarily on the consumer of the project or product, the customer. Therefore, the questions should be:

### The Why: Customer

Without customers the product dies, so this should always be the starting point. We could create the most modular, high-performance, well documented product using the latest tech stack, but if it doesn't solve a problem for any customers it is useless.

To answer this questions there are a few options. We can ask people (potential customers) what problems their facing, where there is friction in processes, or where they aren't satisfied by an existing solution. If we don't have people to ask, we can look at what products might already exist in the market. By doing so we can spot gaps or undeserved segments that could be targeted with solutions. There is also first hand experience. Every day we interact with hundreds of products and multiple problems, so we can draw from our own experiences for problems to solve.

### The What: Product

Now that we have some problems, we need to know what the product will be which can address them. Usually the first thing to ascertain is how much of the target segment will we attempt to capture? A product attempting to capture 100% of a segment will look vastly different from that of a product tailored to a niche 20-30% high-value market segment.

Often we won't get the solution right on the first attempt anyway, or the target market could alter either based on external factors or because we choose to target a different segment. As a result, the product we create needs to be flexible or able to change to fit these changing needs.

### The How: Technology

Finally, after we know **why** there is a problem, and determined **what** the solution would look like we can determine **how** to build the product. At this point, it means we already have quite a number of constraints to work within, so maybe that new shiny technology we wanted to try isn't actually appropriate.

Building a product from new for an emerging or niche market is challenging, and it is unlikely we get the solution right the first time. As such the technologies we pick should be optimized for flexibility and rapid development. Choosing a new language or framework with limited community support and open source libraries will instead slow us down, without any tangible benefit if what we develop needs to be re-built in 2-3 months anyways.

Once we have customers, arguably trust becomes the biggest factor for retention. This means that our product must be reliable, so choosing a new, relatively un-tested technology could be seen as a high risk. This means often what can win is boring, tried and tested technologies that we know works, and there is a wide range of engineers out in the market with that skill set. This allows us to focus on the product development, rather than experimenting with new technologies that we struggle to scale the team with from a narrow pool of talent.

_See [Getting the Product to Customers](../getting-product-to-customers) for a deeper dive in product delivery_

<!-- Diagram showing hierarchy of questions -->
![]()

## The Irony of Creativity



## The Footnote

I would be remised if I didn't address the fact that not all projects need to have a customer. It is entirely reasonable that the purpose of a project is for the sake of learning. If this is the case, then you should definitely pick whatever technology you want to explore. However, you must always take your learnings with a grain of salt. Just because you have learnt a new skill doesn't mean that it should be applied to every new scenario. You must still make a reasonable evaluation if it is fit for purpose in that given use case. For any product, that usually just boils down to "how does this provide value to the customer(s)".

**NOTES**

Illusion of choice: What technology to use?
0\. Intro - What technology is the wrong question, what product and for what customer is the right question

1. Inverted Problem - People are selfish, it's not their fault, they only know what they can see, which is always their PoV. Engineers want to pick what interests them (why, what, how)
2. The why: customer - Product dies without customers, so we start here
3. The what: product - How does the product solve the customer issues? How does it give value
4. The how: technology - How to optimise the what, clear direction, measurable target, feedback loop
5. The irony of creativity - unlimited freedom doesn't produce creativity, constraint does. Starving artist, social commentary, all key art and literature came from constraints
6. Footnote about learnings