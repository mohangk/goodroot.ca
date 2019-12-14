---
title: "Conway's Law Is Real"
author: Kellen Evan
date: '2018-10-13'
slug: practicality-metaphysics-conways-law
description: "People build systems that reflect their communication structures. This is an easy to digest and thoughtful introduction to Conway's Law. Learn how to unlock..."
published: true
---

Some ideas shine with truth. One such idea was articulated in 1967 by computer programmer Melvin Conway:

> “organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations.”

It is often found in good humour: the system is a mess and the people who made it are a mess. Haha -- that's Conway's Law for you! Joking aside, within it holds the potential for a radical leap forward in the development of complex programmatic systems.

## Proving the Law

In 2011, Harvard business school published a paper: [Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/faculty/Publication%20Files/08-039_1861e507-1dc1-4602-85b8-90d71559d85b.pdf). The collaborative work, conducted by MaCormack, Rusnak and Baldwin, applied scientific rigour to Conway's Law.

Under the name "The Mirroring Hypothesis" the group analyzed software patterns. They separated organizations into two groups: **tightly coupled** and **loosely coupled**.

A **tightly coupled** organization has structured communication. Consider a corporate environment where employees dwell under the same roof, report to a manager, who reports to a manager within an intentional structure in organized concert.

On the flip side, an open source project is a prototypical example of a **loosely coupled** organization. Communication occurs between random contributors. It is unstructured, unmanaged and internationally distributed. The contributors are motivated by completing a task and there is minimal - if any - social fabric.

_Table from "A Test of the “Mirroring” Hypothesis"_

|   | Tightly Coupled   | Loosely Coupled   |
|---|---|---|
|  Goals | Shared, Explicit  | Diverse, Implicit  |
| Membership  |  Closed, Contracted | Open, Voluntary  |
| Authority  |  Formal, Hierarchical  |  Informal, Meritocratic |
|  Location | Centralized, Colocated  | Decentralized, Distributed  |
|  Behaviour | Planned, Coordinated | Emergent, Independent  |

A key concept from the study is that of _Propagation Cost_: _"the percentage of system elements that can be effected, on average, when a change is made to a randomly chosen element."_ In other words, the propagation cost is the **overall percentage of a system that is impacted when a function or file is altered**.

By comparing open source projects to projects that were private, then open sourced, the paper established a clear link: tightly coupled organizations create software with significantly higher propagation cost. In contrast, loosely coupled organizations build systems with a much lower propagation cost.

This suggests that loosely coupled systems are more modular and are therefore more approachable. And it provides partial proof of Conway's Law: **systems reflect the communication structures within which they are developed**.

A second study, [The Influence of Organizational Structure on Software Quality: An Empirical Case Study](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-2008-11.pdf) by Nagappan, Murphy and Basili of Microsoft pushed the idea further.

They revealed that Conway's Law is bidirectional. Code level failure metrics indicate poor organizational metrics:

> "...organizational metrics when applied to data from Windows Vista were statistically significant predictors of failure-proneness."

But what were these "organizational metrics" that were collected? And how did these metrics speak towards software failure proneness?

_The following table has been adapted from the article, with the descriptions expanded for clarity and context. Low failure rate is is good, high failure rate is bad._

| Organizational Metric | Quality Indication |
|---|---|
| Number of engineers | The greater the number of engineers that touched the code, the higher the failure rate. |
| Number of ex-engineers | Teams that lost team members had a decline in knowledge retention and therefore an increase of failure rate. |
| Edit frequency | The more edits to a component, the higher the instability and thus failure rate.  |
| Depth of Master Ownership | Components that were "owned" by a "master" -- a single person with 75% or more of edits -- had lower failure rates. |
| Percentage of Org contributing to development | The lower the overall percentage of the organization that contributed to development, the lower the failure rate. |
| Level of organizational code ownership | The more code contributors outside of the core working group, the higher the failure rate. |
| Overall Organization Ownership | The ratio of "masters" making edits to code compared to the total number of engineers. The better the ratio in favour of "master" contribution, the lower the failure rate. |
| Organization Intersection Factor | For each group that contributed 10% or more to a codebase, the higher the failure rate.  |

From the quality indications, we can describe an **"ideal development team"** as one that:

* is small
* has had no churn
* makes few edits
* has an owner of 75% contribution history or more
* does not need to work across an organization
* contains only one working group

The teams' conclusion was thus:

> "... organizational measures predict failure-proneness in Windows Vista with significant precision, recall and sensitivity."

And it proves Conway's Law even further: **organizations can be analyzed to predict quality of programmed work and vice versa**.

It is easy to miss "the forest from the trees" when drawing conclusions from scientific rigour. Social dynamics are so rooted in chaos that one wonders about the repeatability and transferability of these studies. But we emerge with two key take aways and consider them to be true:

**1) Systems reflect the communication structures within which they are developed.**

**2) Organizations can be analyzed to predict the quality of programmed work and vice versa.**

Or, in short: **Conway's Law is true**.

## The Reverse Conway

Conway's Law can help establish organizational structure as projects grow. Proponents of _microservice architecture_ offer social scaling as a key benefit of its methods: architect your code into modular microservices first and then the optimal organizational structure will follow. It's Conway's Law in reverse.

When we think back to the "ideal team", a microservice team will be small, have a "master" and be made up of only one working group. But it can still be impacted by churn, make many updates and work across other organizational teams.

Yet the approach still seems wise on the surface. Compared to tighly coupled, monolithic designs, a loosely-coupled microservice team will proliferate systems that are more approachable and less failure prone. But it cuts the other way in that there will then be a mesh of independent pieces, each vulnerable to the drawbacks of poor communication.

## Conway Yourself

Communication is sometimes called a "_soft problem_". It's emotionally rooted, which is used as the rationale to dismiss its importance. And on the surface that feels fair.

There is evidence that open source projects operate successfully without a long-term plan, organizational structure and any form of social interaction. And it appears as though organizations can "reverse Conway" their systems, using architectural changes to "fix" their people.

But neither approach is good. Neither will scale. They both break down when other engineering, product, marketing and design teams need to contribute. They do not foster collaboration. They do not help **build a team**.

Communication isn't an engineering problem. And it isn't a _"soft"_ problem. It's our default mode. A team optimizes for Conway's Law when it **improves its interpersonal communication**. The technical brilliance of tomorrow will be born from those that learn to minimize ego and **enhance** verbal, non-verbal, emotional and spiritual communication.

So how do you do it? Ask your team mates.
