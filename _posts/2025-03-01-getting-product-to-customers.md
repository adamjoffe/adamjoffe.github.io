---
title: Getting the Product to Customers
date: 2030-03-01 12:30:00 +0000
categories:
  - Product Engineering
tags:
  - product
  - CI
  - CD
  - DevEx
---

## What does the customer want?

Ultimately, customer's have a problem that they need to solve, and to solve the problem they will look to the market to find a product that does this for them. As the creators of a product, we need to ensure that our developed product fits the customer's needs, this is the [product market fit](https://www.productplan.com/glossary/product-market-fit/).

Finding this product market fit almost always involves iteration and innovation, as you're very unlikely to get it right first time out. Therefore, getting the product out there to collect customer feedback and continuously enhancing the product to address their problem is the way forward.

This feedback loop, drives customer engagement and desire for the products, ultimately driving sales providing value to the business and keeps you in the job. So this should also be what you want!

## Building the product pipeline

To gain the true benefit of the customer feedback loop the product pipeline must be constructed to allow enhancements to be made to the product as regular as possible, even multiple times a day!

Now to build this pipeline, a simple recipe can be followed:

1. Mono environment
2. Auto deployment
3. Shift left
4. Metrics
5. Experiment

### Step 1 - Mono Environment

Mono environment refers to having a single environment to which our product (the code) is deployed. No staging, no UAT, just production. This removes the "standard" promotion pattern of deployment which slows how quickly you can get the product to your customer's.

One concern with a mono environment, is that code, functionality and features must be delivered in chunks. This must be avoided to reduce the risk of outages or issues on both the existing product and the new features. The solution is to involve "dark launching" or "feature flags" in production. This means deploying iterable chunks of code into production, hidden from the customer's using conditional logic based on the user interacting with our product.

### Step 2 - Auto Deployment

Now we have a mono environment, let's speed up delivery even more! A Continuous Deployment (CD) pipeline is critical, not just a Continuous Integration (CI) pipeline. Once we merge our code and validate it is correct, there is nothing else to do with only one environment but ship it to prod!

To make this easier, [trunk based development](https://trunkbaseddevelopment.com/) approach to version control simplifies everything. This makes it clear to all contributors that what is deployed in production is what is merged to the main branch.

### Step 3 - Shift Left

We have one environment and everything merged to main is auto-deployed, how do we gain confidence in what we deploy?  Without staging or UAT environments to hide behind, we need to [shift left](https://en.wikipedia.org/wiki/Shift-left_testing) for our testing. This also means that as product engineers, we have to wear our QA caps. One very good way to ensure this is to follow a [Test Driven Development (TDD)](https://martinfowler.com/bliki/TestDrivenDevelopment.html) approach. Writing our tests before implementing the feature to ensure what we test accurately represents the behaviour we desire.

Shifting left doesn't, and shouldn't, stop at testing. Given we are always auto-deploy to production, we should also toss in our infrastructure and security concerns. If we're deploying on any modern cloud solution, luckily we can leverage [terraform](https://www.terraform.io/) for our needs. This empowers our shiny CD pipeline to also ensure that any compute, event, monitoring, etc. is in place when we move straight to production.

Likewise, for security, we should ensure our CI pipeline is equipped to scan our package dependencies **and** the artifact(s), often a Docker image, that will be deployed. One key thing we can't avoid is that vulnerabilities can be discovered **after** we have deployed our product. This means we can't solely rely on only the CI pipeline to protect us, since it only runs when we make changes. So additional continuous scanning must be employed to keep our product, and the customer's, safe.

### Step 4 - Metrics

The product is ready to be used by the customers, we are able to rapidly enhance and make changes to it with our strong engineering pipeline. What is missing? How do we know what our customers want? How do we know the product is succeeding? We should do what any scientific field does, measure it!

There are a huge range of products out there to help gather, store, view, represent and explore user metrics. Covering these is not the point of this discussion, we we'll digress. What we want to measure is our customers interaction with our feature flows/journeys:

1. What features customers are using
2. How long it takes them to go through various feature journeys
3. Customer drop off rate through a journey

With this, we can see what features benefit customers, pinpoint potential bottlenecks in the flow and identify friction points.

### Step 5 - Experiment

Finally, we can use all these gathered metrics to improve our product. Firstly, by leveraging the usage, we can prioritise what are the high value features to work on. Then roll out experimental changes behind our feature flags, targetting reducing drop-off and/or speeding up journeys. Using segmentation functionality of the feature flags we can [A-B test](https://www.optimizely.com/optimization-glossary/ab-testing/) our changes to determine if there was a real improvement for our customers!

TODO: wrap up sentence

## Scaling the product business

TODO: discuss scaling

## Being Selfish

Another hidden benefit, more selfish than helping customers, is this method of software development if significantly more pleasant to work on and more self gratifying. Being agile in enhancing a product reduces our own feeling of friction and pain points. This increase to the developer experience almost entirely removes process bureaucracy and eliminates those silly hoops we are sometimes forced to jump through. If nothing else, don't do this for the product, do it for yourself.

TODO: images
