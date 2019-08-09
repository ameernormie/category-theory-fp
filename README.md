# Category Theory

---

Table of Contents

- [1.1 Motivation and Philosophy](#motivation-and-philosophy)
- [1.2 What is a Category](#what-is-a-category)

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

## What is a Category

Three major things

- Abstraction
- Composition
- Identity

Once you abstract, things that look different start looking the same.
For example, two snooker red balls may have different scratches but you can replace one with another.

**Composition and Identity define category theory**

`A category is a bunch of objects`

Objects and morphisms

**_Composition_**
For every composable pair of arrows `a------f------->b------g-------->c` i.e. end on one is the beginning of other.
Then there must be an arrow going directly from `a--------gof------->c` also written as `gof` meaning `g after f`

**_Identity_**
For every object in the category there is an identity for this object.
It is Identity because of the composability.

if `a` is composed **f** with the `identity of b`, we get back arrow `f`.
`a------------f-------------id(b)` .
we can write it as **id(b) after f = f**

`left identity` ===> id(b) after f : **`a------------f-------------id(b)`**
`right identity` ===> g after id(a) : **`id(a)------------g-------------b`**

another axiom of the category is

`a--------f---------b-----------g------------c------------h---------------d`

**h after(g after f) = (h after g) after g**
