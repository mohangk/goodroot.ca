---
title: "Conway's Law Is Real"
author: Kellen Evan
date: '2018-10-13'
slug: practicality-metaphysics-conways-law
description: "People build systems that reflect their communication structures. This is an easy to digest and thoughtful introduction to Conway's Law. Learn how to unlock..."
published: true
---

Conway's Law was first articulated in 1967 by computer programmer Melvin Conway and within it holds the potential for a radical leap forward in the development of complex programmatic systems:

> “organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations.”

## Proving the Law

In 2011, Harvard business school published a paper: [Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/faculty/Publication%20Files/08-039_1861e507-1dc1-4602-85b8-90d71559d85b.pdf). The collaborative work, conducted by MaCormack, Rusnak and Baldwin, studied what they called _"The Mirroring Hypothesis"_ and analyzed software patterns. During their analysis they separated organizations into two groups: **tightly coupled** and **loosely coupled**.

* A **tightly coupled** organization is a typical corporate software development environment where employees dwell under the same roof, report to a manager, who reports to a manager, within an intentional structure in organized concert. It has structured communication that bends to the physical confines of the workplace.

* A **loosely coupled** organization is best exemplified by an open source project. Communication occurs between random contributors, it is unstructured, unmanaged and the workforce is most often distributed. The contributors are motivated by completing a task and there is minimal -- if any -- social fabric.

_Table from "A Test of the “Mirroring” Hypothesis"_

|   | Tightly Coupled   | Loosely Coupled   |
|---|---|---|
|  Goals | Shared, Explicit  | Diverse, Implicit  |
| Membership  |  Closed, Contracted | Open, Voluntary  |
| Authority  |  Formal, Hierarchical  |  Informal, Meritocratic |
|  Location | Centralized, Colocated  | Decentralized, Distributed  |
|  Behaviour | Planned, Coordinated | Emergent, Independent  |

A key concept from the Harvard study is that of _Propagation Cost_: _"the percentage of system elements that can be effected, on average, when a change is made to a randomly chosen element."_ In other words, the propagation cost is the **overall percentage of a system that is impacted when a function or file is altered**.

By comparing open source projects to projects that were private, then open sourced, the paper establishes a clear link: **tightly coupled** organizations build systems with significantly **higher** propagation cost while **loosely coupled** organizations build systems with a much **lower** propagation cost.

The reason appears to be that loosely coupled systems do not share any existing social context and therefore their authors write more approachable code so anyone may alter the system without that context. Open source authors are aware that their code will be seen by the broad public and similar to a writer cleaning up their language for a broad audience, so the programmer does with their code. It is a function of applied empathy for the reader or next contributor. The study, and its implications, provides partial proof of Conway's Law: **systems reflect the communication structures within which they are developed**.

Why does a tight-knit physical structure product more tightly coupled systems? If you and your peers gather around one computer to solve a problem and "co-author" a solution, deep context is presumed inside of the solution. There is little motivation to factor in clarity and approachability and their modularized expressions into the code because the interaction made the context apparent to all relevant contributors. Now repeat this for the development of most of the system and you can see how a "shared social mind" will result in a "contraction" of the programmatic surface area.

A second study, [The Influence of Organizational Structure on Software Quality: An Empirical Case Study](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-2008-11.pdf) by Nagappan, Murphy and Basili of Microsoft pushed the idea further. They revealed that Conway's Law is bidirectional and that code level failure metrics indicate poor organizational metrics:

> "...organizational metrics when applied to data from Windows Vista were statistically significant predictors of failure-proneness."

What were these "organizational metrics" that they collected? How did these metrics speak towards software failure proneness? And does this mean that _code_ can be analyzed to see where _organizations_ need to change?

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

This is fascinating and it pushes the proof of Conway's Law even further: **organizations can be analyzed to predict quality of programmed work and vice versa**. But it is easy to miss "the forest from the trees" when drawing conclusions from other software systems given the near infinite nature of their complexity. And social dynamics are so rooted in chaos that one wonders about the repeatability and transferability of these studies. But this is science and so we emerge with two key take aways and consider them to be true:

**1) Systems reflect the communication structures within which they are developed.**

**2) Organizations can be analyzed to predict the quality of programmed work and vice versa.**

Or, in short, we agree that **Conway's Law is true**.

## The Reverse Conway

Conway's Law can help establish organizational structure as projects grow. Proponents of _microservice architecture_ offer social scaling as a key benefit of its methods: architect your code into modular microservices first and then the optimal organizational structure will follow. It is marketed as Conway's Law in reverse.

It is a fair approach as when we think back to the "ideal team", a microservice team will be small, have a "master" and have only one working group. But it can still be impacted by churn, make many updates and work across other organizational teams, and it may even need to do so more often. Yet the approach is still wise from a pure technical perspective even with the social caveats.

Compared to tightly coupled monolithic designs, a loosely-coupled microservice team will proliferate systems which are more approachable and less failure prone. But it cuts the other way in that there will then be a mesh of independent pieces, each vulnerable to the drawbacks of poor inter-dependent communication. Ten microservice teams with staffed by poor communicators will render a poor system in aggregate, no matter how competent the programmers, no matter how "API-like" they behave. It may be better, but it only scratches the surface of where you can generate the most improvement.

It is not so simple to look at a system and reverse architect a team around it to make the system yield in a healthier direction. The inverse is true and it is not so simple to look at a team and re-architect them in hopes of creating an ideal representation of a technical system. There is too much afoot, too much human chaos, to attempt either feat of social engineering. Only if communication is the highest order concern and area of focused intent will whatever linkage between human and system reach an optimal state. We cannot escape this reality, no matter how bad our social skills are as an industry.

## Conway Yourself

Communication is often called a "_soft problem_". It is rooted in emotion, spirit, and chaos, and that is why people over-engineer to try to work around it. On the surface this human avoidance feels fair as there is evidence that open source projects operate well without a long-term plan, organizational structure or any form of social interaction. It also appears as though organizations can "reverse Conway" their systems, using architectural changes to "fix" and "analyze" their people. But both approaches break down fast because either of them will scale or build good teams or healthy environments.

Communication is not an engineering problem and it is not a _"soft"_ problem. It is a human problem and it is the hardest problem and the one that most engineers lack the courage to address head-on. A team optimizes for Conway's Law not when it rearranges people like furniture but when it creates an environment where each person is inspired and expected to **improve their interpersonal communication** instead of trying to tool over it or engineer around it. The technical brilliance of tomorrow will be born from those that learn to minimize ego and **enhance** verbal, non-verbal, emotional and spiritual communication.

So how do you do it? Ask your team mates.
