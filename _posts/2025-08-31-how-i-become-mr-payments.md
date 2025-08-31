---
title: How I Became "Mr. Payments"
date: 2025-08-31 12:30:00 +0000
categories:
  - Software Engineering
  - Product Engineering
tags:
  - Architecture
  - Growth
  - Learning
  - Domain
  - Knowledge
  - Subject Matter Expert
---

## Origins

![Mr. Payments Knowledge](../assets/img/posts/2025-08-31-images/mr-payments-knowledge.png)

"Mr. Payments" was a title given to me about a year into my time working at a [B2B](https://en.wikipedia.org/wiki/Business-to-business) bank. I had joined the payments team, which was responsible for the entire end-to-end payments pipeline and experience:

* Clearing: The real exchange of money between two financial institutes on the behalf of the customers
* Ledger: The atomic record keeper of inbound and outbound monetary movements for each customer account
* Transaction Monitoring: The tracking of inbound and outbound monetary movements for customers to check for fraudulent activity or signs of money laundering
* User experience: The interactive web or mobile interface that provides a rich set of features
* Security: The systems in place to protect the customers accounts and money from bad actors, ensuring trust is maintained for the financial institute

Previous to this I had worked in FinTech within other spaces (e.g. market surveillance, loan origination) but never in a payments space. The only partially applicable skill I had was from my time working in market surveillance. During this time I was in the team responsible for writing algorithms to spot suspicious or illegal activities on exchange markets, which only tangentially related to transaction monitoring. From this almost zero knowledge start, within the timespan of the year, I was able to become a subject matter expert in this domain and able to lead projects, manage key stakeholders, and drive product direction.

In this post, I want to discuss my approach to learning within a new space, and how to build up your knowledge at light-speed to become an invaluable asset.

## Starting

![Mr. Payments Starting](../assets/img/posts/2025-08-31-images/mr-payments-starting.png)

When approaching a new space where you don't have any prior domain knowledge, there will be an almost overwhelming amount of information to take in. The way I approach this is to start by grouping information into categories which I then use to compartmentalise the knowledge. This breaks things down from an excessively large, amorphous problem space into discrete components which can be more easily comprehended. When doing this, it is important to remember that this is never going to be perfect, since correctly dividing up the space requires complete knowledge (similar to what we see in the [data model paradox](../data-model-paradox)). This means as you build up the knowledge, these categories will change, shift, and intersect with each other. This is entirely expected and reflects the intertwined nature of a all domain spaces. Allowing this to happen will also help you later when you can draw on these overlaps to build valuable associations which help when applying your problem solving skill set.

Once we have some rough starting categories, the next step is gather as much knowledge as possible. When reading documentation, discussing in meetings, or even reading pull requests, always ask further questions. Even if you think you can correctly assume the answer from your existing knowledge, these clarifying questions convert assumptions to tangible facts. One key note here is to try avoid unnecessarily derailing conversations when a large group of people are involved (think 8+ engineers). You want to be able to scale your own knowledge, but this shouldn't be at the cost of a lot of engineering time, and doesn't have to be either! The better approach in these scenarios is to take notes of your questions during the conversations and then asking them to a more senior member after. This provides the same outcome to you, but without any downside to the wider team. Worse case, you will derail the engineer you talk to, which at most may drag 1 or 2 further people in. Even then, from my experience, when this occurs you usually get a net benefit. Since a senior member was required to bring in others, that means there was already a lack of clarity that will now be fixed.

## Building

![Mr. Payments Building](../assets/img/posts/2025-08-31-images/mr-payments-building.png)

With a structured knowledge base to pull from and an engine to continually build on it, we can get our hands dirty in the code! Attempting to consume the entire codebase at once is a futile effort, even at the scale of a small startup. Before getting too in the weeds of the business logic, orient yourself with the architecture, design, and infrastructure of the code first. To do this, always lean on first principals, so instead of asking *"what technologies are being used?"* ask instead *"what aspects are prioritised in our infrastructure? consistency? resiliency? throughput? latency?"*. This way you will gain a deeper insight into what is most important in our system, e.g. which part of [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem) did we optimise for? This has the added benefit of making it significantly easier to identify if a wrong decision was made once you have a more complete view. This approach will allow you to build up a comprehension of all the connected pieces which make up the architectural foundation (like Lego!).

After understanding the broader brush strokes, then you get stuck into *"real"* changes. When working on the code, it is always quicker to pair with an experienced engineer, who can guide you through what is needed. This promotes a knowledge transfer which will kickstart your progress. However, I would always argue that in the long run, extended pairing will restrict your eventual understanding, and worse case create a bias on *"how"* things should be done in the system. As such, after the first few sessions of pairing, you should go on alone, pushing you to work through problems which challenge your understanding. A critical caveat here is to not get bogged down forever, you must time box how long you're willing to get stuck before reaching out for guidance. This will be subjective and vary person to person, but you'll need to use to trial and error to determine what works for you. My general rule of thumb is that if I am feeling stuck, I will take a 20-30min break away from my computer. If I return and can't progress in 10-15min, then I will reach out for guidance. This approach will feel painful, you will often feel hopeless at times, but I guarantee that it will force you to gain a better understanding as well as highlight the pain points of the codebase.

Finally, the last trick that I can suggest is once you have a *"complete working change"* don't just stop there. Take the opportunity to experiment with what you've done. Ask yourself:

* What happens if I change the way I am constructing data?
* What happens if I alter my test setup or mocks?
* What happens if the order or operations are reversed?
* Are there any edge cases that were already missing?
* Can I refactor shared logic to make reasoning about the code easier?
* Should I add a comment to clarify any nuances?

In the best case, this will result in an iteratively better solution than your first approach. Even if it doesn't, it will always give you some valuable knowledge. Within your solution, also take care to explore how things function under the hood. For instance, if there is a framework feature, or test mock that is being leveraged, go explore how it works and play around with altering how the interface is being used. Whilst you are unlikely to work on the innards of these things, there is a lot value you gain in understanding it that reading documentation, which treats it as a black box, won't be able to teach you. A black box is useful for abstraction and compartmentalising, but it will ultimately restrict you from your full potential.

## Retro

![Mr. Payments Retro](../assets/img/posts/2025-08-31-images/mr-payments-retro.png)

Once your knowledge is built up and you have a reputation as a domain expert, you will reach a limit. As a single person you can't scale infinitely. Therefore, the primary lever is to scale through others. Whilst being the holder of a significant amount of knowledge is beneficial, it ultimately results in a burden for you and a bottleneck for others. To avoid this, you should try to offer information to others in a self-serve manner. For this, you should look towards what information you have that others may be missing, or will likely seek in the future, and then **document**! The approach to constantly consider what knowledge others may not have shouldn't just stop at documentation. This should always be at the forefront of your mind when communicating with as well. From their perspective, it is very hard to understand the depth of an unknown problem space, so the pertinent questions know how to ask will be limited. As such, when knowledge sharing a topic you are well versed on, don't dive straight into the fine details that interest you or are the most complicated. Instead, start with broader context and lead your audience into the depths of the domain. This way, you can ensure you avoid them making misleading assumptions or being confused due to any perceptions they may have.

Helping others by walking through code/concepts with them doesn't just help them, it also helps you! When explaining a concept for others, they may not understand it in the perspective you view it. As such, you will be forced re-orient your views on the subject, creating a more complete outlook on the knowledge you hold. This is the result of [reflective learning](https://en.wikipedia.org/wiki/Reflective_learning). Your colleagues aren't the only ones with which the approach of viewing things from others perspectives is beneficial. The same should be done with the scariest of taskmasters - customers! However, this one is different to your colleague. Your colleagues work in the field (software engineering) and sector (i.e. FinTech, Health Tech, Game Dev, etc.) with you, so will have an rough understanding and foundational knowledge to pull from. Customers on the other hand come from a huge range of backgrounds, to the point where there could be no real shared understanding between you and them. As such, you'll need to stretch much further to put yourself in their shoes. Doing this won't improve your technical knowledge like explaining architecture or implementation concepts to your colleague, instead it will improve your product knowledge as you work to understand the need of the customer. One isn't better than the other, as both are critical to become a fully rounded domain subject matter expert with your own catchy title!

So continue to always ask yourself, *"if I am person X, what would I understand about the domain, and what is the most critical thing I should know"*. With complete information you have, you can now answer any question they have even before they ask it!
