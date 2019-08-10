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

**Example:**
We have a basic category that we use in programming
`Objects` are types and `arrows` are functions.
Any single argument function takes an argument of type `a` and returns the result of type `b`.
So, a `function is a morphism between two types`.

- Types are your objects
- Functions are your arrows (morphisms)

##### What are Types:

They are just sets, sets of values. Instead of types we'll be saying sets of values. functions are functions between sets. sets and functions, types and functions.
function ---> Mathematical function

A function is a mapping from one set to another.

##### Category

If we build a category on top of this logic, I have to forget about the structure.
We know sets but we don't know whats inside them. It has no structure.

Suppose there are two sets `A` and `B`. We know the sets but not thier structure also we know how many arrows (morphisms) are going from one set to another but we don't know what these arrow are doing. I just know how many are there. I can also compose them. I know how to compose functions on sets. And ofcourse there is also an identity function on sets. And now I have a category set.

I forgot about everything about functions, what these objects do and I ended up with a category set.

##### Category set:

I have objects that now I forgot where they came from, I have these arrows that now I forgot where that came from. But, now I have the multiplication table, composition table for them. And this `composition table` fulfills my axioms of category theory.
Compositions are associative, identity.
In this category set, I don't care about the structure of my objects or the structure of my functions or morphisms.

`Now I can start thinking about what I can say about these objects just by looking at morphisms`
And it turns out I can say a lot of things about them just by looking at morphisms.
I can identify a lot of things just by looking at morphisms.

- Is the set empty
- Is the set a single value set
  ...

If you are thinking about what's inside a set, you are thinking about assembly language of sets, about the elements of the set, how they are mapped. Category theory gives you this higher level language in which you don't have to look inside the set, you just have to look how they are connected with arrows. It's the ultimate data hiding. You have this object, a data set but you cannot look inside of it. It shrunk to a single point. All you have is it's interface.
`Interface is how it connects to other objects. All these arrows coming out of the object and into the object`

If you take this idea of data hiding this is where it really shines, this is the end of the road for abstraction.
