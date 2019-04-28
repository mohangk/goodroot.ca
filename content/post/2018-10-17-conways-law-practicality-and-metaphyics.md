---
title: "Conway's Law, Practicality & Metaphysics"
author: Kellen Evan
date: '2018-10-13'
slug: practicality-metaphysics-conways-law
published: true
---

Some ideas shine with truth. One such idea was articulated in 1967 by computer programmer Melvin Conway:

> “organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations.”

It is often found in good humour. The dysfunctional product: the system is a mess and the people who made it are a mess. Haha -- that's Conway's Law for you! Joking aside, it holds the potential for a radical leap forward in the development of complex programmatic systems.

## Proving the Law

In 2011, Harvard business school published a paper: [Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/faculty/Publication%20Files/08-039_1861e507-1dc1-4602-85b8-90d71559d85b.pdf). The collaborative work, conducted by MaCormack, Rusnak, and Baldwin, applied scientific rigour to Conway's Law.

Under the name "The Mirroring Hypothesis", the group analyzed software patterns. The study separated organizations into two groups: **tightly coupled** and **loosely coupled**.

A **tightly coupled** organization is one with structured communication. It may be a corporate environment where employees dwell under the same roof, report to a manager, who reports to a manager, and who operate within an intentional structure in organized concert.

An open source project is a prototypical example of a **loosely coupled** organization. Communication occurs between random contributors. It is unstructured, unmanaged and internationally distributed. The contributors are motivated by completing a task and there is minimal social fabric, if any.

_Table from "A Test of the “Mirroring” Hypothesis"_

|   | Tightly Coupled   | Loosely Coupled   |
|---|---|---|
|  Goals | Shared, Explicit  | Diverse, Implicit  |
| Membership  |  Closed, Contracted | Open, Voluntary  |
| Authority  |  Formal, Hierarchical  |  Informal, Meritocratic |
|  Location | Centralized, Colocated  | Decentralized, Distributed  |
|  Behaviour | Planned, Coordinated | Emergent, Independent  |

A key concept from the study is that of _Propagation Cost_: _"the percentage of system elements that can be affected, on average, when a change is made to a randomly chosen element."_ In other words, the propagation cost is the **overall percentage of a system that is impacted when a function or file is altered**.

By comparing software systems which began as open source projects to those that were private, then opened, the paper established a clear link. Tightly coupled organizations create software with significantly higher propagation cost. In contrast, loosely coupled organizations build systems with a much lower propagation cost. Loosely coupled systems are more modular and are therefore more approachable.

And so the first key take away is: **systems reflect the communication structures within which they are developed**.

A second study, [The Influence of Organizational Structure on Software Quality: An Empirical Case Study](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-2008-11.pdf) by Nagappan, Murphy, and Basili of Microsoft pushed the idea further. It revealed that:

> "...organizational metrics when applied to data from Windows Vista were statistically significant predictors of failure-proneness."

This proved that Conway's Law is bidirectional: code level failure metrics indicate poor organizational metrics. And what were the organizational metrics that they collected? And how did these metrics speak towards software failure proness?

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

From the quality indications, we can dsecribe an **"ideal development team"** as one that: 

* is small
* has had no churn
* makes few edits
* has an owner of 75% contribution history or more
* does not need to work across an organization
* contains only one working group

The article's conclusion was thus:

> "... organizational measures predict failure-proneness in Windows Vista with significant precision, recall and sensitivity."

The conclusion highlights the second key take away: **organizations can be analyzed to predict quality of programmed work and vice versa**.

It is easy to miss 'the forest from the trees' when drawing conclusions from scientific rigour. Social dynamics are so rooted in chaos that one wonders about the repeatability and transferability of these studies. But, we emerge with two key take aways and consider them to be true:

**1) Systems reflect the communication structures within which they are developed.**

**2) Organizations can be analyzed to predict the quality of programmed work and vice versa.**

Or, in short: **Conway's Law is real**.

## The Reverse Conway

To optimize for Conway's Law and establish organizational structure as projects grow, proponents of _microservice architecture_ offered a solution:

> "When looking to split a large application into parts, often management focuses on the technology layer, leading to UI teams, server-side logic teams, and database teams. When teams are separated along these lines, even simple changes can lead to a cross-team project taking time and budgetary approval. A smart team will optimise around this and plump for the lesser of two evils - just force the logic into whichever application they have access to. Logic everywhere in other words. This is an example of Conway's Law in action." - Martin Fowler, [Microservices](https://www.martinfowler.com/articles/microservices.html).

The approach appears wise. A microservice team will be small, likely have a "master" and be made up of one working group. But when we think back to an "ideal team", a microserivice team can still be impacted by churn, make many updates, and work across an organization. 

Microservice proponents will point to 'smart endpoints, dumb pipes' and 'you build it, you run it' as social/technical maxims to address some of these higher level concerns. And they're right, to an extent. Compared to busy monolithic designs, loosely-coupled microservice teams proliferate systems that are more approachable and less failure prone. But it cuts the other way in that the organization now has a mesh of independent pieces, each individually vulnerable to the drawbacks of poor communication.

## Conway Yourself

Communication is often called a "_soft problem_". It is emotionally rooted, which is used as the rationale to dismiss its importance. It isn't code, it isn't tangible and it isn't logical. Naturally, attempts to alter the soft social dynamic of a software engineering team are not often met with enthusiasm. 

And it makes sense as to why. There is evidence that open source projects successfully operate without a long-term plan, organizational structure or even social interaction. And it appears as though you can "reverse conway" your systems, using system architectural changes to "fix" your people. But neither approach is good. Neither will scale. They break down when other engineering, product, marketing, and design groups need to contribute. They do not develop effective collaboration. 

Communication is not an engineering problem. And it isn't a _soft_ problem. It is one of the hardest problems there is. It is ubiqutious; you can't escape it. We take the leap when we improve our communication with others. The teams that learn to minimize ego and **enhance** verbal, non-verbal, emotional, technical and spiritual communication will reach the highest of heights, building the brilliant things that today are constrained by contemporary discourse. 

So how do you do it? Ask your team mates.

[Return to homepage.](/)
