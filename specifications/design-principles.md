# Design Principles

> Source of truth: [EROAD Design Principles (Confluence)](https://eroad.atlassian.net/wiki/spaces/UD/pages/4587520052/Design+Principles)
> Last synced: 2026-05-18 (page version 5)
## Context: a B2B platform

EROAD's products are B2B: our users are professional operators — drivers, fleet
managers, compliance officers, dispatchers — using our products as part of their
paid work, often under time pressure, in the field, and alongside other systems.
This context shapes how every principle below should be applied:

- Users don't choose our products for fun; they need to get a job done and get back to work. Efficiency and clarity outrank delight.
- Our products often sit inside a broader operational workflow (fleet, compliance, logistics), so consistency and predictability matter more than novelty.
- Mistakes and downtime have real operational and financial consequences for our customers' businesses, not just individual users.
- Accounts, permissions, and data are frequently shared across an organisation — design decisions must account for roles, oversight, and shared context, not just a single end user.

EROAD's design principles put people at the centre of everything we build, with
**Empowered Productivity** as our north star. These principles guide every design
decision, from early discovery through to delivery and beyond.
## Design for People

Our platforms need to be positively and profitably used by real people. Our work
should always complement and enhance and never impede an individual's use of our
products, regardless of their circumstances.

**In practice:**

- Design for the real context of use: in a cab, on a worksite, in a depot, often under time pressure
- Use language and concepts familiar to the user's world, not ours
- Ensure every feature works regardless of ability, device, or connectivity
- Prioritise the needs of the person in front of the screen, not the system behind it
## Design for Trust

Our products do what they're intended to do, every time. We consistently exceed
expectations through measurably superb experiences that are powered by accurate,
reliable, and timely information.

**In practice:**

- Always show the user what the system is doing and why
- Be consistent: same patterns, same language, same behaviour everywhere
- When something goes wrong, be clear, honest, and helpful about what happened and what to do next
- Only surface data that is accurate and current; never mislead through ambiguity or omission

## Design for Simplicity

Our users are busy, so our interactions need to be fast, simple and a pleasure
to use. Performing tasks should be drop-dead simple, allowing our users to reach
their goal at speed.

**In practice:**

- Remove anything that does not serve the user's immediate goal
- Minimise memory load: make options visible and decisions obvious
- The best interface is the one the user doesn't have to think about
- Streamline the most common tasks; let complexity stay hidden until it's needed
## Design for Scalability

Allow the interface to scale with large and small amounts of data and onto any
device. Designing components that are highly performant in all situations is
paramount in supporting our users.

**In practice:**

- Design components that work equally well with 1 row or 10,000 rows of data
- Ensure layouts adapt gracefully across screen sizes and devices
- Build patterns that remain consistent and performant as the product grows
- Avoid hardcoding assumptions about data density, fleet size, or user volume
## Design for Action

We strive to turn data into meaningful, useful, and actionable information. We
empower users by identifying outliers, discrepancies between forecasted and
actual outcomes, and call attention to key issues. We shine a light on what
they may not know.

**In practice:**

- Surface the most important information first; don't make users hunt for it
- Turn raw data into clear signals: what's normal, what's an outlier, what needs attention
- Every screen should answer: what should I do next?
- Make it easy for users to act on what they've seen, without leaving their workflow
## Design for Assurance

A sense of progress and clarity is embedded into every interaction to enable
effective communication for our users and their customers. Each feature is
designed to improve users' lives in a measurable way.

**In practice:**

- Every interaction should confirm progress: loading states, success messages, clear outcomes
- Help users understand the impact of their actions before and after they take them
- Make errors recoverable, understandable, and non-threatening
- Measure the success of each feature by whether it genuinely improves a user's working life
## Reference heuristics

We also refer to [Jakob Nielsen's 10 usability heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/)
as a core reference when evaluating and critiquing design work.
