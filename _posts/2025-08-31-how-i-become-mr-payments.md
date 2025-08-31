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

"Mr. Payments" was a title given to me about a year into my time working at a [B2B](https://en.wikipedia.org/wiki/Business-to-business) bank. I had joined the payments team which was responsible for the entire end-to-end payments pipeline and experience:

* Clearing: The actual exchange of money between two financial institutes on the behalf of the customers
* Ledger: The atomic record of inbound and outbound monetary movements for each customer account
* Transaction Monitoring: The tracking of inbound and outbound monetary movements for customers to check for fraudulant activity or signs of money laundering
* User experience: The web or mobile interface users interactive with that provides a rich set of features
* Security: The systems in place to protect the customers accounts and money from bad actors, ensuring trust is maintained for the financial institute

Previous to this I had worked in other FinTech spaces (e.g. market surveillance, loan origination) but never in a payments space. The only somewhat applicable skill I had was from my time working in market surveillance. During this time I was in the team responsible for writing algorithms to spot suspicious or illegal activities on exchange markets, which only tangentially relates to transaction monitoring. From this almost zero knowledge start, within the space of the year, I was able to become a subject matter expert in this area and able to lead projects, manage key stakeholders, and drive product direction.

![Mr. Payments Knowledge](../assets/img/posts/2025-08-31-images/mr-payments-knowledge.png)

In this post, I want to discuss my approach to learning within a new space, and how to build up your knowledge at light-speed to become an invaluable asset.

## Starting

When approaching a new space where you don't have any prior domain knowledge, there will be an almost overwhelming amount of information to take in. The way I approach this is to immediately start grouping information into categories which I use to compartmentalise the knowledge. This breaks things down from an excessively large, amorphous problem space into discrete components which can more easily be comprehended. When doing this, it is never going to be perfect, since correctly dividing up the space requires complete knowledge (similar to what we see in the [data model paradox](../data-model-paradox)). This means as you build up the knowledge, these categories will change, shift, and intersect with each other, this is entirely expected and will reflect the intertwined nature of a domain space. Allowing this to happen will also help you later when you can draw on these overlaps to build valuable associations when applying your problem solving skill set.

Once we have some rough categories, the next step is gather as much knowledge as possible. When reading documentation, discussing in meetings, or even reading pull requests, always ask further questions. Even if you think you can correctly assume the answer from your existing knowledge, these clarifying questions convert assumptions to tangible facts. One key not here is to try avoid derailing conversations where a large group of people are involved (think 8+ engineers). You want to be able to scale your own knowledge, but this shouldn't be at the cost of a lot of engineering time, and doesn't have to be either! The better approach in these scenarios is to take notes of your questions during the conversation and then asking them to a more senior member after. This provides the same outcome to you, but without any downside to the wider team. Worse case, you will derail the engineer you talk to, which at most may drag 1 or 2 further people in. Even then, from my experience, when this occurs you usually get a net benefit due to the need of the senior member bringing in others means that there was a lack of clarity that will now be fixed.

## Building

With a structured knowledge base to pull from and an engine to continually build it, now we can get our hands dirty in the code. Attempting to consume the entire codebase at once is a futile effort, even at the scale of a small startup. Before getting too in the weeds of the business logic, orient yourself with the architecture, design, and infrastructure of the code. To do this, always lean on first principals. What this means is rather than asking *"what technologies are being used?"* ask instead *"what aspects are prioritised in our infrastructure? consistency? resiliency? throughput? latency?"*. This way you will gain a deeper insight into what is most important in our system. This has the added benefit of making it significantly easier to identify if the wrong decision was made once you have a more complete view. This approach will allow you to build up a comprehension of all the connected pieces which make up the architecture foundation (like Lego!).

After understanding the broader brush strokes, then you get stuck into *"real"* changes. When working on the code, it is always quicker to pair with an experienced engineer who can guide you through what is needed. This promotes a knowledge transfer which will kickstart your progress. However, I would always argue that in the long run, extended pairing will restrict your eventual understanding, and worse case create a bias on *"how"* things should be done in the system. As such, after the first few days or pairing, you should go on alone. A critical caveat here is to not get bogged down forever. You must time box how long you're willing to get stuck before reaching out for guidance. This will be subjective and vary person to person, but you'll need to use to trial and error to determine what works for you. My general rule of thumb is that if I am feeling stuck, I will take a 20-30min break away from my computer. If I return and can't progress in 10-15min, then I will reach out for guidance. This approach will feel painful, you will feel like it is a bit hopeless at times, but I guarantee that it will force you to gain a better understanding as well as highlight the pain points of the codebase.

Finally, the last trick that I can suggest is once you have a *"complete working change"* don't just stop there. Take the opportunity to experiment with what you've done. Ask yourself:

* What happens if I change the way I am constructing data?
* What happens if I alter my test setup or mocks?
* What happens if the order or operations are reversed?
* Can I refactor shared logic to make reasoning about the code easier?
* Should I add a comment to clarify any nuances?

In the best case, this will result in an iteratively better solution than your first approach. Even if it doesn't, it will always give you some valuable knowledge. With the approach, take particular care to explore how things function under the hood. For instance, if there is a framework feature, or test mock that is being leveraged, go explore how it works and play around with altering how the interface is being used. Whilst you are unlikely to work on the innards of the thing, there is a lot value in understanding it, which reading documentation which treats it as a black box, won't be able to teach you. A black box is useful for abstraction and compartmentalising, but it will ultimately restrict you from your full potential.

## Retro

Once your knowledge is built up and you have a reputation as a domain expert, you will reach a limit. As a single person you can't scale infinitely. The primary lever is to scale through others. Whilst being the holder of a significant amount of knowledge is beneficial, it always results in being a burden for you and a bottleneck for others. To avoid this, you should try to provide information to others in a self-serve manner. For this, you should always attempt to see what information that you have that others may be missing or will likely seek in the future, and then **document**! This approach to always consider what knowledge others may not have shouldn't just stop at documentation. This should always be at the forefront of your mind when communicating with anyone. From their perspective, it is very hard to understand the depth of an unknown problem space, so the pertinent questions they can ask will be limited. As such, when knowledge sharing a topic you are well versed on, don't dive straight into the fine details that interest you or are the most complicated. Instead, start with broader context and lead your audience into the depths of the domain. This way, you can ensure you avoid them making misleading assumptions or being confused due to perceptions they may have.

Helping others by walking through code/concepts with them doesn't just help them, it also helps you! By being forced to explain a concept in a way for others the way in which you understand it may not work for them. As such, you will be forced to have a more complete view on the knowledge you hold. This ends up helping you as well to see things from a new perspective through [reflective learning](https://en.wikipedia.org/wiki/Reflective_learning). Your colleagues aren't the only ones with which the approach of seeing things from their point of view is a benefit. The same should be done with the scariest of taskmasters - customers, however, this one is different to your colleague. Your colleagues work in the field (software engineering) and sector (i.e. FinTech, Health Tech, Game Dev, etc.) with you, so will have an rough understanding or foundational knowledge to pull from. Customers on the other hand come from a huge range of backgrounds, to the point where there could be no real shared understanding between you and them. As such, you'll need to stretch a bit further to put yourself in their shoes. Doing this won't improve your technical knowledge like explaining concepts to your colleague, instead it will improve your product knowledge as you work to understand the need of the customer. One isn't better than the other, as both are citical to become a fully rounded domain subject matter expert with your own catchy title!
