---
title: "Conway's Law, Practicality & Metaphysics"
author: Kellen Evan
date: '2018-10-13'
slug: practicality-metaphysics-conways-law
published: true
---

Some ideas, more so than others, shine with a deeper truth. One such idea was articulated in 1967 by computer programmer Melvin Conway:

> “organizations which design systems … are constrained to produce designs which are copies of the communication structures of these organizations.”

It is often found in good humour. The dysfunctional product: the system is a mess and the people who made it are a mess. Haha -- that's Conway's Law for you! Apart from applied silliness, within this informal law lies the potential for a radical leap forward in the development of complex programmatic systems.

## The Weeds

In 2011, Harvard business school published a paper: [Exploring the Duality between Product and Organizational Architectures: A Test of the “Mirroring” Hypothesis](https://www.hbs.edu/faculty/Publication%20Files/08-039_1861e507-1dc1-4602-85b8-90d71559d85b.pdf). The collaborative work, conducted by MaCormack, Rusnak, and Baldwin, applied scientific rigour to Conway's Law.

Under the name "The Mirroring Hypothesis", the group analyzed patterns within software systems. The study separated software into two groups, those which are tightly coupled and those which are loosely coupled.

A tightly coupled organization is one with structured communication. For example, a corporate environment where employees dwell under the same roof, report to a manager - who reports to a manager - and who operate within an intentional structure in organized concert.

On the other hand, an open source project is a prototypical example of a loosely coupled organization. Its communication is unstructured among many contributors, has no management, and no shared location. The contributors are motivated by completing a task and there is minimal social fabric, if any.

_Table from "A Test of the “Mirroring” Hypothesis"_

|   | Tightly Coupled   | Loosely Coupled   |
|---|---|---|
|  Goals | Shared, Explicit  | Diverse, Implicit  |
| Membership  |  Closed, Contracted | Open, Voluntary  |
| Authority  |  Formal, Hierarchy  |  Informal, Meritocracy |
|  Location | Centralized, Colocated  | Decentralized, Distributed  |
|  Behaviour | Planned, Coordinated | Emergent, Independent  |

A brilliant concept from the study is that of _Propagation Cost_. It is described as: _"the percentage of system elements that can be affected, on average, when a change is made to a randomly chosen element."_ In other words, the propagation cost is the overall percentage of a system that is impacted when a function or file is altered.

By comparing software systems which began as open source projects to those that were private, then opened, the paper establishes a clear link. Tightly coupled organizations create software with significantly higher propagation cost. In contrast, loosely coupled organizations build systems with a much lower propagation cost. These systems are more modular and therefore more approachable, or loosely coupled.

And so the take away is: **systems reflect the communication structures within which they are developed**.

A second study, [The Influence of Organizational Structure on Software Quality: An Empirical Case Study](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-2008-11.pdf) by Nagappan, Murphy, and Basili of Microsoft pushed the idea further. The study revealed that:

> "...organizational metrics when applied to data from Windows Vista were statistically significant predictors of failure-proneness."

Fascinating! Organizational metrics predict failure-proneness. And the reverse is also true: code level failure metrics indicate poor organizational metrics. But what _were_ these organizational metrics that were collected?

_The following table has been adapted from the article, with the descriptions expanded for clarity and context. Note that high quality is low failure proneness, low quality is high failure proneness._

| Category  | Description  |
|---|---|
| Number of engineers | The greater the number of engineers that touched the code, the lower the quality. |
| Number of ex-engineers | Teams that lost team members had a decline in knowledge retention and therefore overall quality. |
| Edit frequency | The more edits to a component, the higher the instability and lower the quality.  |
| Depth of Master Ownership | Components that were "owned" by a "master" -- a single person with 75% or more of edits -- had higher quality. |
| Percentage of Org contributing to development | The lower the overall percentage of the organization that contributed to development, the higher quality. Speaks towards small, focused groups. |
| Level of organizational code ownership | The more code contributors outside of the core working group, the lower the quality. |
| Overall Organization Ownership | The ratio of "masters" making edits to code compared to the total number of engineers. The better the ratio in favour of "master" contribution, the higher the quality. |
| Organization Intersection Factor | For each group that contributed 10% or more to a codebase, there was a decline in quality.  |

In my interpretation of the study, an **ideal development team** is one that: is small, has had no churn, makes few edits, has an owner of 75% contribution history or more, does not need to work across the overall organization, and contains only one working group. The article's conclusion was thus:

> "Our organizational measures predict failure-proneness in Windows Vista with significant precision, recall and sensitivity."

And so our second key take away is: **organizations can be analyzed to predict quality of programmed work and vice versa**.

In summary, research is always helpful. But it is _really_ dry and it is easy to miss 'the forest from the trees' when drawing conclusions from scientific rigour. Social dynamics are so rooted in chaos that one wonders about the repeatability and transferability of these studies.

We shall emerge from the weeds with two solid premises in tow and consider them to be true:

**1) Systems reflect the communication structures within which they are developed.**

**2) Organizations can be analyzed to predict the quality of programmed work and vice versa.**

## Microservices by Conway

Phew. We needed some hard analysis to define parameters... But communication is ultimately a "_soft problem_". It is emotionally bound and systemic attempts to over-control social dynamics within software engineering organizations is not met with enthusiasm.

This is evident by the dire state of the 'managerial' concept. We have _product owners_, _tech leads_, and _scrum masters_, but we do not have - nor seem to want - managers, or any other form of social or spiritual advisement. Logically so, as it is evident that open source projects successfully operate without a long-term plan, organizational structure, or even social interaction. But what is the alternative?

Clever technical folk try to socially engineer communication by altering the system instead of the social structure. To optimize for Conway's Law and establish organizational structure as projects grow, proponents of _microservice architecture_ present a solution:

> "When looking to split a large application into parts, often management focuses on the technology layer, leading to UI teams, server-side logic teams, and database teams. When teams are separated along these lines, even simple changes can lead to a cross-team project taking time and budgetary approval. A smart team will optimise around this and plump for the lesser of two evils - just force the logic into whichever application they have access to. Logic everywhere in other words. This is an example of Conway's Law in action." - Martin Fowler, [Microservices](https://www.martinfowler.com/articles/microservices.html).

The approach seems wise. A microservice team will be small, likely have a "master", and be made up of one working group. But when we think back to Microsoft's **ideal team**, that group might still be impacted by churn, make many updates given cross-functionality, and work across an organization. Microservice proponents will point to 'smart endpoints, dumb pipes' and 'you build it, you run it' as social/technical maxims to address some of these higher level concerns.

Interesting. But it seems this approach creates more dimensions within which we may apply Conway's Law. Each microservice team is now at risk of being constrained by its own communication structures, and so too the overall architecture constrained by the communication between each microservice team.

If we took an 'empirical' look at a team built around a microservice, what would we unearth as our indicators of quality? There will be variance, but what will govern it?

Compared to busy monolithic designs, loosely-coupled microservice teams proliferate systems that are more approachable and less failure prone. Visually, one inter-tangled circle becomes several smaller circles with lines of clean connection.

But it cuts the other way in that one now has more independent pieces, each individually vulnerable to the drawbacks of poor communication. Those smaller circles are themselves at risk of becoming entangled. No matter how we try to engineer out of the problem, the fact remains: communication must be excellent in order for systems to become excellent.

## Debug Yourself

Open source projects present an intriguing reality. As long as individuals can speak the same mutual language, the code, then they are able to contribute. Factors such as time, personality, location, and so on, are less important.

This method has been successful in producing quality systems of a loosely couple nature. Is it then true that the right idea is to operate loosely, like an open source project? Or is there something that organizations can do to _be better_, to engineer a more effective social system that itself creates better systems?

Communication structures live in deep complexity and are fractal in nature. We can follow them to great depth, inward and outward, to a limitless degree: systems, influenced by systems, influencing systems.

This not just an engineering problem. It is a natural one. It is a social one. We walk the brightest path by improving our communication. The organization that learns to minimize ego and **enhance** verbal, non-verbal, emotional, technical, and spiritual communication will reach the highest of heights, building things unfathomable given the constraints of the current mode.

The most important point is **you**. Your mind is an organization of systems, thoughts, biases, and patterns which reflect, and are constrained by, other systems of communication. If one is destined to reproduce systems upon systems -- your thought patterns, your own individual narratives -- where do we start? What do we change?

It is easy to get lost within ego, succumbing to pretense, doubt, conflict, and selfishness. It is much more difficult to operate in truth, to breath and slowdown, to look someone in the eye, open yourself, risk being wrong or awkward, and have a candid, expansive, and respectful conversation. Better systems start when we look at ourselves, inwards and outwards, together.
