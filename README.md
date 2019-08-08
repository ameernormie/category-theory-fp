# Category Theory

---

Table of Contents

- [1.1 Motivation and Philosophy](#motivation-and-philosophy)

## Motivation and Philosophy

- What does it have to do with programming?
- Why is category theory important?
- Is category theory only relevant to functional programming?

Divide the problem in small chunks. Find the solution for small chunks and in the end combine the solutions of small chunks in to one big solution. This is called composability.

**Why not OOP?**
Objects hide implementation and they hide exactly the wrong thing. Which makes them un-composable.
Objects hide two things.

- Mutation
- Sharing

They often share data between themselves. Mixing sharing and mutation has a name, it's called `data race`.
So, Objects in OOP are abstracting over `data race`. You are not supposed to hide that. because when you start combining different objects you get free data races. Data races are bad.

Functional approach doesn't mutate data so there are no data races.

`Category theory is a higher level language above all languages. It's not a practical language that we can write code in.`

**Practical Motivation**
We want to get to this higher level of abstractions to help us abstract ideas that later can be translated into programs.

**Philosophical Motivation**
Category theory unifies a lot of things. If you abstract enough on top of all unnecessary stuff then suddenly all these things start looking similar. From that high level all programming languages start looking similar.
At this high level other thing look the same. There is this unification of all areas of mathematics in category theory.
