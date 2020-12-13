---
title: "Conway's Law Is Real"
author: Kellen Evan
date: '2018-10-13'
slug: practicality-metaphysics-conways-law
description: "People build systems that reflect their communication structures. This is an easy to digest and thoughtful introduction to Conway's Law. Learn how to unlock..."
published: true
categories:
    - Technology
---

Conway's Law was first articulated in 1967 by computer programmer Melvin Conway and within it holds the potential for a radical leap forward in the development of complex programmatic systems:

> “organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations.”

## Proving the Law

In 2011, Harvard business school published a paper: [Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/faculty/Publication%20Files/08-039_1861e507-1dc1-4602-85b8-90d71559d85b.pdf). The collaborative work, conducted by MaCormack, Rusnak and Baldwin, studied what they called _"The Mirroring Hypothesis"_. The study analyzed software patterns to better understand the relationship between people and the systems they create. 

During their analysis they separated organizations into two groups, **tightly coupled** and **loosely coupled**:

* A **tightly coupled** organization is a typical corporate software development environment where employees dwell under the same roof, report to a manager, who reports to a manager, within an intentional structure in organized concert. It has structured communication that bends to the physical confines of the workplace.

* A **loosely coupled** organization is best exemplified by an open source project. Communication occurs between random contributors. It is unstructured, unmanaged and the workforce is most often distributed. There is minimal -- if any -- social fabric.

_Table from "A Test of the “Mirroring” Hypothesis"_

|   | Tightly Coupled   | Loosely Coupled   |
|---|---|---|
|  Goals | Shared, Explicit  | Diverse, Implicit  |
| Membership  |  Closed, Contracted | Open, Voluntary  |
| Authority  |  Formal, Hierarchical  |  Informal, Meritocratic |
|  Location | Centralized, Colocated  | Decentralized, Distributed  |
|  Behaviour | Planned, Coordinated | Emergent, Independent  |

A key concept used to frame their findings is _Propagation Cost_. 

They defined it as:

> "the percentage of system elements that can be effected, on average, when a change is made to a randomly chosen element."

A function or file has a propagation cost which indicates **the overall percentage of the system that is impacted when it is altered**. By comparing open source projects to projects that were private, then open sourced, the paper established a clear link: **tightly coupled** organizations build systems with significantly **higher** propagation cost while **loosely coupled** organizations build systems with a much **lower** propagation cost.

The reason seems to be that loosely coupled systems do not share any existing social context, and therefore their authors write more approachable code so that anyone can make alterations to the system with minimal context. In other words: open source authors are aware that their code will be seen by the broad public and, similar to a writer cleaning up their language for a broad or international audience, so the programmer does with their code. It is a function of applied empathy for the reader or the next contributor.

But why does a tight-knit, tightly coupled physical structure produce more tightly coupled programmatic systems? We can imagine you and your peers gathered around one computer to solve a problem and "co-author" a solution. Deep context is presumed inside of the solution as you all think through it together, in the office, over lunch, or wherever you go. There is little motivation to factor in clarity and approachability and their modularized expressions into the code because the interaction made the context apparent to all relevant contributors. Now repeat this for the development of most of the system and you can see how a "shared social mind" will result in a "contraction" of the programmatic surface area and a binding of the undocumented creative context between those present.

The study, and its implications, provides partial proof of Conway's Law: **systems reflect the communication structures within which they are developed**.

A second study, [The Influence of Organizational Structure on Software Quality: An Empirical Case Study](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-2008-11.pdf) by Nagappan, Murphy and Basili of Microsoft pushed the idea further. It revealed that Conway's Law is bidirectional, and that code level failure metrics can also indicate poor organizational metrics:

> "...organizational metrics when applied to data ... were statistically significant predictors of failure-proneness."

But what were these "organizational metrics" that they collected? And how did these metrics speak towards software failure proneness? 

And does this mean that _code_ can be analyzed to see where _organizations_ need to change?

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

After developing a means to determine what success and failure look like within a system, the teams' conclusion was thus:

> "... organizational measures predict failure-proneness ... with significant precision, recall and sensitivity."

This is fascinating! And it pushes the proof of Conway's Law even further: **organizations can be analyzed to predict quality of programmed work and vice versa**. But it is easy to "miss the forest from the trees" when drawing conclusions from other software systems given the near infinite nature of their complexity. And social dynamics are so rooted in chaos that one wonders about the repeatability and transferability of these studies. But this is science and so we emerge with two key take aways and consider them to be true:

**1) Systems reflect the communication structures within which they are developed.**

**2) Organizations can be analyzed to predict the quality of programmed work and vice versa.**

Or, in short, we agree that **Conway's Law is true**.

## The Reverse Conway

Awareness of Conway's Law can help organizations establish healthy social structures as projects grow. Microservice archicture, for example, offers social scaling as a key benefit of its method: architect your code into modular microservices first and then the optimal organizational structure will follow. It is marketed as Conway's Law in reverse. Simpler, tidier systems with healthy communication create simpler, tidier teams with healthier communication, or so it's suggested.

It is a fair proposal, as when we think back to the "ideal team" a microservice team will be small, have a "master" and have only one working group. But it can still be impacted by churn, make many updates and work across other organizational teams, perhaps even more often. 

Yet the approach is still wise from a pure technical perspective even with the social caveats. Compared to tightly coupled monolithic designs, a loosely-coupled microservice team will proliferate systems which are more approachable and less failure prone. But it cuts the other way in that there will then be a mesh of independent pieces, each vulnerable to the drawbacks of poor inter-dependent communication. 

Ten microservice teams staffed by poor communicators will render a poor system in aggregate, no matter how competent the programmers and no matter how "API-like" they behave. It may be better than the chaotic, monolithic alternative, but it only scratches the surface of where you can generate the most improvement.

It is not so simple to reverse architect a technical system around a team to make it healthier. It is also not at all simple to look at a team and re-architect _them_ in hopes of creating an ideal representation of a technical system. There is too much afoot, too much human chaos, to attempt either feat of social engineering. Only if communication is the highest order concern will whatever linkage between human and system reach an optimal state. We cannot escape this reality.

## Conway Yourself

Communication is often called a "_soft problem_". It is rooted in emotion, spirit, and chaos, and that is why we see weak teams try to over-engineer around it. On the surface this human avoidance feels appropriate, as there is evidence that open source projects operate well without a long-term plan, organizational structure, or any form of social interaction. It also appears as though organizations can "reverse Conway" their systems, using architectural changes to "fix" and "analyze" their people. But both approaches fail, because neither of them will scale towards thriving teams or healthy environments.

Communication is not an engineering problem, and it is not a _"soft problem_". It is a human problem, the hardest problem, and the one that most teams lack the courage to remedy. A team optimizes for Conway's Law not when it rearranges people around code like furniture, but when it creates an environment where each person is inspired and expected to **improve their interpersonal communication** instead of trying to tool over it or engineer around it. The technical brilliance of tomorrow will be born from those that learn to minimize ego and enhance their verbal, non-verbal, emotional and spiritual communication.

So how do you do it? Ask your team mates.
