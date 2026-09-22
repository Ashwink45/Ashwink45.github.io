---
title: De-Clouding Movement - A major shift from the cloud infrastructure
description: My thoughts on cloud architecture and why companies might prefer hybrid cloud 
pubDate: 2026-03-15
updatedDate: 2026-03-15
heroImage: ../../assets/cloudimg.png
author: Ashwin
tags:
  - cloud
  - architectural
  - movement
---

# Why Are Some Companies Moving Away From the Cloud?

For years, the direction of modern infrastructure seemed almost obvious: move to the cloud.

AWS, Google Cloud, and Microsoft Azure made it possible for companies to provision servers, databases, storage, and networking without owning physical infrastructure. Startups could scale quickly, teams could deploy globally, and companies could avoid managing their own data centers.

But something interesting has been happening.

Some companies that already moved to the cloud are now moving certain workloads back to infrastructure they control.

This is often called **cloud repatriation**, or more broadly, the **de-clouding movement**.

It does not necessarily mean that companies are abandoning the cloud completely. Instead, they are asking a more specific question:

**Does every workload actually need to run in the public cloud?**

## The Problem With the "Everything in the Cloud" Approach

Cloud computing provides flexibility, but that flexibility comes at a price.

For workloads that are unpredictable, rapidly changing, or geographically distributed, paying for on-demand infrastructure can make a lot of sense.

But consider a different situation.

Imagine a company running the same servers 24 hours a day, every day, with fairly predictable traffic.

Instead of buying hardware once and operating it for several years, the company is effectively renting computing capacity continuously.

At small scale, the convenience can easily justify the cost.

At larger scale, however, the economics can become very different.

Companies also have to account for storage, networking, data transfer, managed databases, monitoring, and other services. Over time, these individual costs can become a significant infrastructure bill.

That is where some companies have started reconsidering their cloud strategy.

## Dropbox: Building Its Own Storage Infrastructure

One of the earlier examples is **Dropbox**.

Dropbox initially relied heavily on Amazon S3 for storing customer files. As the amount of data grew, the company decided to build its own storage infrastructure, which became known as **Magic Pocket**.

By 2016, Dropbox said that Magic Pocket was storing and serving more than 90% of its users' data on its own infrastructure. The company described the motivation in terms of controlling the hardware and software stack, improving performance for its particular workload, and operating more efficiently at its scale. :contentReference[oaicite:0]{index=0}

What makes Dropbox interesting is that this wasn't simply an anti-cloud decision.

Dropbox continued using AWS where it made sense.

The company effectively built a **hybrid infrastructure model**, owning the infrastructure that made economic and technical sense while continuing to use cloud services where they were useful. :contentReference[oaicite:1]{index=1}

## 37signals: A More Visible Cloud Exit

Another widely discussed example is **37signals**, the company behind Basecamp and HEY.

In 2022, 37signals announced that it would begin moving significant workloads away from AWS and Google Cloud.

The motivation was largely economic.

The company reported spending around **$3.2 million per year** on cloud infrastructure and concluded that some of its relatively predictable workloads could be operated more economically using its own hardware. :contentReference[oaicite:2]{index=2}

37signals purchased its own servers and placed them in colocation facilities.

The company later reported that its cloud spending had fallen substantially as the migration progressed. In 2024, it reported an annual cloud bill of around $1.3 million, compared with the earlier $3.2 million figure. :contentReference[oaicite:3]{index=3}

The migration eventually extended to its large S3 storage footprint. In 2025, 37signals began moving petabytes of data from Amazon S3 to its own storage infrastructure. :contentReference[oaicite:4]{index=4}

By January 2026, the company described the major S3 migration as complete, including the movement of billions of files without downtime. :contentReference[oaicite:5]{index=5}

The interesting lesson here is not simply that 37signals left the cloud.

It is that the company looked at its **specific workload characteristics** and decided that owning the underlying infrastructure made more sense for those workloads.

## GEICO: Repatriation at a Completely Different Scale

The idea becomes even more interesting when looking at a much larger organization.

GEICO spent years moving applications into public cloud infrastructure. According to reporting from The Stack, its cloud spending eventually exceeded hundreds of millions of dollars annually, prompting the company to rethink its infrastructure strategy. :contentReference[oaicite:6]{index=6}

GEICO has been rebuilding parts of its infrastructure using technologies including **OpenStack, Kubernetes, and Open Compute Project hardware**.

This is not simply a return to the traditional data center.

Instead, GEICO is effectively building a private infrastructure platform using many of the same software ideas that made cloud computing attractive in the first place.

The goal is greater control over infrastructure economics and architecture while still retaining modern automation and orchestration.

## So Is the Cloud Actually Dying?

Not really.

The examples above are better understood as a shift from **cloud-only thinking to workload-specific infrastructure decisions**.

The cloud remains extremely useful when a company needs:

- Rapidly changing capacity
- Global infrastructure
- Managed services
- Short-lived workloads
- Easy experimentation
- Infrastructure without large upfront capital costs

But other workloads may have different requirements.

For example:

- Large and predictable compute workloads
- Massive amounts of long-term storage
- Consistent 24/7 utilization
- Workloads where data transfer costs are significant
- Systems requiring greater control over hardware

For these workloads, owning or colocating infrastructure can sometimes make economic sense.

## The Real Movement Is Hybrid

What I find most interesting about de-clouding is that the debate is often presented as:

**Cloud vs. On-Premises**

But that is probably the wrong way to look at it.

A more useful question is:

**Where should each workload run?**

A company might keep its analytics platform in the cloud, operate its core databases on owned hardware, use a public cloud for burst capacity, and maintain another provider for disaster recovery.

This creates a hybrid infrastructure model where different workloads live in different environments based on their requirements.

Dropbox's infrastructure evolution is a good example of this approach, while 37signals demonstrates what a much more extensive repatriation can look like. :contentReference[oaicite:7]{index=7}

## What Makes Cloud Repatriation Difficult?

The financial calculation is only one part of the decision.

Running your own infrastructure means taking responsibility for things that cloud providers normally handle:

- Hardware procurement
- Capacity planning
- Networking
- Storage management
- Hardware failures
- Backups
- Disaster recovery
- Security
- Monitoring
- Infrastructure maintenance

There is also a significant engineering cost involved in moving workloads.

Data has to be transferred, systems need to be tested, dependencies have to be identified, and downtime has to be avoided.

That means simply comparing a cloud bill with the price of a server does not give you the complete picture.

The real comparison is between the **total cost of ownership** of both approaches.

## What I Find Interesting About the Movement

The biggest takeaway for me is that infrastructure decisions are becoming less ideological.

The cloud was never simply about renting servers.

It introduced an entirely different way of thinking about infrastructure: APIs instead of hardware procurement, automation instead of manual configuration, and elasticity instead of fixed capacity.

De-clouding does not necessarily reject those ideas.

Instead, companies are beginning to ask whether they can keep those software and operational principles while changing where the underlying hardware runs.

That is what makes the movement interesting.

The future may not be completely cloud-based or completely on-premises.

It may simply be **more deliberate about where workloads belong**.

## Conclusion

The de-clouding movement is not a story about companies suddenly abandoning AWS, Azure, or Google Cloud.

It is a story about companies reaching a certain scale, examining their infrastructure costs and workload characteristics, and deciding that some workloads may be better served elsewhere.

Dropbox built its own storage infrastructure.

37signals has moved a large portion of its workloads and storage away from public cloud infrastructure.

GEICO is rebuilding parts of its infrastructure around private-cloud and open hardware technologies. :contentReference[oaicite:8]{index=8}

The common idea is simple:

**Cloud is a tool, not a requirement.**
