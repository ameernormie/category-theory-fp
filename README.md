# Category Theory

---

Table of Contents

- [1.1 Motivation and Philosophy](#motivation-and-philosophy)
- [1.2 What is a Category](#what-is-a-category)
- [2.1 Functions, Epimorphisms](#functions-and-epimorphisms)
- [2.1 Monomorphisms, Simple Types](#monomorphisms-and-simple-types)

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
- ...
- ...

If you are thinking about what's inside a set, you are thinking about assembly language of sets, about the elements of the set, how they are mapped. Category theory gives you this higher level language in which you don't have to look inside the set, you just have to look how they are connected with arrows. It's the ultimate data hiding. You have this object, a data set but you cannot look inside of it. It shrunk to a single point. All you have is it's interface.
`Interface is how it connects to other objects. All these arrows coming out of the object and into the object`

If you take this idea of data hiding this is where it really shines, this is the end of the road for abstraction.
![](https://lh3.googleusercontent.com/Ge1s-ZmLRuNZT9GLcKpvrRF0BkrtGaMXhDNFoy9BgxvJ2z7P9SzGawXVw6aJ3ZEw7LSSaen6TNlb2WZVEQ9rRubiFMD-B1BPzDIsgEOZAGMMv0E2sujPmfhgwXmexAOaI-5yxwEeQIJ79QOppTAmLAepTdl1NL_ZPo8RogfjJEqE2neumijCCjYV0epoc1RQ4WlFvHMgLzMuFFiGAC8OW6glZpgYqPMRNQ60D4pqvga-F9baPC4sGQCrCCpOWwAB55AdraM1eWrp0jVBqL2UZpEtPoP2k7fKnUttq5AHiLQs31sDFp4mkEJaJnxylsZZ3_Jhiga8QpS4XgI293jHfavYq2VPURXpDS7KF0ms_TcI4oNqkteVDejskQbJT5bxLnykAWVOTKNPbS4DupOqrpO65oDbbsKQ3ATC0ni9usAOSiiG4soo_LQGDIGbcZHrci0ryJItTzWnY8H4_BfllmXO0phv1AAOBOvntvv6dNuIo_sJwfToL8lvs89ZMvKZIhpc8Av3Mo1XyWT7Qd5eNyj-bY4YOry3rhVZa4LM2nrlfL78kHK6B1-beycIKUi1gW2J_xMPKEBUhOVJ052aTADo5lZT9a1cOkD0_mx0S5TniEILTQ1QnYFnaiYEWoWOu7achtOf_Pru8zKGOrixrZw=w1372-h1832-no)
![](https://lh3.googleusercontent.com/J-prFq5tTD7I-enuCDY-ZBi9w_DD2YMG76uo561HsNwZcPM9Zm0FKV60i5AWJe90TIIklQg1No2J9bwttHfVZAJ_70B9twBN2sRqwqvzheHE048axBPOxdXMZefKB387BoM1bjpoxzmqWFAfbtq0jc59MurT040myUQ1Kur0SUd_B7wgPnIjDzqNgqJaJjA_UkaYcI6C6KZcx4pcp2Lvby26b-0pCoJbexekDU7pNvp_7HKMEHXY7kcKtIlFMfCnz6U87-sEqRBwBTE2gCAgIAIhQ3GxqxoGh9F4WkjH66_8vYgmWccg8PccN6nhoHCqlDjeB-D4WkkADcLlGq_dtYfRUskkFcvDaMChryn8X8gqIa3j4c9Ri_nGfnKDPjtItIXcAU8VpN7CiN5jGqLZ3U4EyMDASdtJaV7Uk-SuEuwZUttUhE_FUpDdYoZxJoHZX_ePn0vQVEtWMumC964qOwDKHWlZw7ias58xhg8a6F7QJiB1SOph6HH3PmBKEWaZnJ4Z8PZNcplHjYZhygUqS5Bh_8z-3cDIywUs8c4XrBdnNOGcLXau8qqZoReb7kmaaTGFMb-Vmw2c-rJO-B0PNtyhTv7OsRXRASGgfu5oNd2SEyRWaXC8OQYhB98PCDyxIY2AxbGSngk3zkobQH7Epn8=w1672-h1832-no)
![](https://lh3.googleusercontent.com/vbAOXTdrSkHCXzrZj3uJfcmnjCWSXywYEJLRYFWu-VD0dhdPhTwcc2SgYOLCISInSnIezuwIA6-ddX4iXB1AEJL7ZoNjDZKaHmSZsFze5b30LKnjydi2tFhlYtQ3Z-q2PpIwgEuU85nbtzXuV-6LTSm0SSPr5LBVUaD5GyVPha6qj6BXOVR_YDT-Wwk1565cBPQm4SxiTCPBsAEwbctDEgTANxO6V2ooq4Q5XCMInkaIURV6AK7LQrNLaT3pA9vnetXIdhtmkm8JRNuKHpFU-KTiTZ7it-K_2FmZT2-HdTSRl_VT9USPVOBzsUUsdWcoJe_qxOLPfVJTOh5f0zdXoA1MnpTH7gQLILbtg0WCXxyzImuhIur2SdG9JRwjrVfPwZpu_Kz1sFYM4s2GUrw9WH4xbnbvQhJkCLLiUoEF58y1pvTpYHXnFVREPmwbp34EOvWi2h0eCoxbGEw0MrW5vXUZKWlUZcTT-NyfBWaLDzHI8R6r_qsBueOkbL29jLuY9xm5bWFAqEt7Q7OPI8MUeJbM-g7W2P2V-osjTcVw-S24nLfYTd2D1_thguiY_1pvbzo6GDVQck40PmxI94M9JCQ903IuO8g3-Vb61SToiP341vn4JpW98OkfECEumzuRBH_hAQss8Nwa-Q3XxtnKFnc=w1396-h1832-no)
![](https://lh3.googleusercontent.com/b8pWrimkP9A6iOedKNk1RPyBxV-yWhyI_5_exVMl_CLqHk0Ub_r5Oli57rlb8ULRE3PthUamhhR0tmxZhCinweHNFqJ3Ysq736MSzKf5Z_1IYu_VyGdt-R8_Vwe5pibNUdOw7BePgJkwwRWPyW4DeNXCOV_dtFHskKP-Jr50Plo_Ziw6Gx8eewvoifwP0UT4XaUxV72Rx5kuiemn-I_7q6aTXLwxw5yO7QNZGZjilWXIBvJpUhd4mKen6EUE5xJN-Snbn8vXGoWkdPlXOgB2GcxTtA3oK-vrpkLcdzYqfA39CBBqvim1zfl9ESaNuOGTMfweP0IRhbB9IOoNAwKc_PucbFDkBJDKmTYtb3B28AFqOpNoCTxZr6q1FgWpjieia59wjbUV8ebaAAyIu4fK7zYuWCxXz8nGjNrv87FlhwZkBxbhJ_EnrbMOIX0fsyIV1dEFbvrZWHSvLoA681Re8Jfb34tRgLnwLv9a0P5Fu6AIwUaKyNHGlpoLKvryOA8J9N66GsSg51uWodtTiFzQQgB8B0i-VARN7VQineBK3gGnOdknmVLwBPY4Wj1u26y0REnRqf97nhEtlxiP1_ik6QMHKMGaVFHwAfX_L2oVHSxCQ5eGfwx4ryC-4GxRIx7aulR59l0SFQyskJbMw8JAaf4=w2584-h760-no)

## Functions and Epimorphisms

When you write a language you have to define the semantics of the language.

- Operational Semantics
- Denotional Semantics

##### Operational Semantics

You define operations of language, how one expression can be transformed in to other.

##### Denotional Semantics

You actually map it to another area that you understand, in particular the most interesting way of mapping is to map it to mathematics. You build a mathematical model and you say `this statement in the language corresponds to some mathematical thing, and this mathematical thing for types is set of values and for functions it's a function between sets`

A function in programming is not exactly the function in mathematics. By function between sets we really mean a `pure function` or a `total function`. because a mathmatical function is defined for every argument, not just for some arguments. This is the major source of problem in programming, we have these partial functions, functions are defined for some arguments and not the other.

`A total function is defined for all arguments`.
**- How can you tell if a function is pure?**
`A function is pure if you can memoize it`. Which means, you can turn it into a lookup table, because for a unique argument it returns a unique value and you can remember it.

**- But the question is, how can you program using only pure functions? We need side effects**
Pure function is an atom, the building block of programs. We can build stuff on top of the pure functions by composing even including side effects (I/O).

#### Functions

We have to look at the functions from a different perspective. We have to look at them at how we can use them as `morphisms` in our category.
Functions are defined in mathematics as a special kind of relation.
Relation is just a subset of pairs of elements. In general, relations does not have directionality, functions are set of arrows going from a particular direction to the other.
what kind of condition we have to impose on a relation to become a function?
![](https://lh3.googleusercontent.com/jJvzE65oD9ktqeTFfkn74jDh4p5_UZ22-KLkrMNxdv712bMu3UGGGEGsObzMdSZ4T4PBFqrsDA9RLzoVnwbcW9th8kFVYhc0l0JMyh-u7urU887luWlHn285YxA_rkSU9YwCfxqxxBZ7RoaxobDRauHTVpAYj1YCJLQM-1q_CjSOx7Lj1jbtVoH8trC6cKi4hKik8OPEoWISGYqaN7WemxGsWqMnl7Wy5_FzMpgFySAKI-HSF9LqKCXiJIaHwGc9NNw_hoIgX63dKbptQmFdZ1WxoLzzyWvui_ThmqTflUBhCfTsgrYrp7ulhbZDV4CAgGPkPK-rg5Xv-g_7nLZMY9ZAhN7TUpwaKkaJfRtdpdc_VDV_UqhuP1G3cEP33Iijcw1BQ4i_awt4nFPBR1kFsT9pP73N7HxWIYFHAMAVznXq8Ht86Q8_5SYzZbpaGRshpX5GBaVePT_kQVJ5nFFEidauddwLfneKsdXmImPcbXll0tNG37OUaIskFND4KcrWWqBnbM-k0lu2ERs89jVhPpyZoe2DzaSD0fBystCVl_AuQDjVR2Csz1Jb149LjrIJF-42Jkr5chqsZoX5JbI92MJkJSDu1InJQ4lPw5WGTQzW-paXlZ5eCQiwJAfTc7Yn7eQTyITFUo63WNSODi715VA=w1812-h1834-no)
![](https://lh3.googleusercontent.com/0-fuWBUmZEw_YXH1W8gyaTqX2uK9LSU0-_srVc2kVYMQpSordNBebVlIqHQvJt8sDXStUh9QCNG8ZKBUkNIrbwPdabsr_cHFkQTXn5Enryd-L5WstxYpSUnyYJWte5d8SpjWMJi5KAAw6E3GN80f895uPH50UorkmVsLd7CdKvWuqmluLXmklw3MUkHB_N0J0pHhp9FzsvfCWg0PpVAnd9Gch_XohRUARjIIU9goH6Cr6_fY7TxGZuvW7ZlvsPyUFu6Vjv1HexGGY5HSP0z4MppHFinW57We8K3qYL1SAWq7fsWhbSQB8-zwT6SYSwdVfOqsoC0DtVlcXUQebxJmcWClA-vnq6f8-XZjB8J6clgSyPUMlKXa6CADeeF68bkT9AU4Y10kyqAUkDNiKOYrWjCDdzWjucm6aZGrceg5eF8CALFrtJqgadDBenYJMy69m8Rot9WSOptHBB4iscthKnp_Zaf6QZWsScgRwx8qEBZUXxOZMEafzTw_4U9TY7k0z6WHwFckwkE4Vc_8MpRtwHh74mU9JZoYMdBiCRnVYmDltO6NQBvM7GuQTq3rJpytWfMJnH_32ixyL0I3HLx-9F3SPt85_ILMuFXEYCTc4HT6bTkXHs6CLUDH65YNLb2LVeOvDD1S69HW_32prZdZUXw=w1542-h1832-no)
![](https://lh3.googleusercontent.com/HExUOTo_hemxnfqcp6gA5N1vZn4ej2tK0ewkIG8Ujg_tJunlN7gerUf_aPDR04RlTozf31pcFUsShoNBqVuw3JqWSYvSI_DCEBviQ2VF3eraNxQPCau8JdpA52AkuZeeu9aS4HIn5Jg-lhbQpE2dltjnCGLEiKdOAxm3v7_QdZRdq6tlY86VH3Xo_dWxwt4jJPrBMiFxib8tXCc0CthSUGfqWPbY-gGF5d8dvZG_nfeZ-ChsbSnPI431ts3s54urYESkfmpDxlNJebxb2aDg_nGsHBTGFj0_bPKZFRJIbg3ahZhruT3JFenKbeqk5MNv2eaPVGFJeq_vwkSzIIRrJpCXJ_1o8o_UOxuIzMYD_t0bT0f20oq1hwfdDxNMRivyklQBsUh7owZqcK0ZSUh8Zdp33R9LdZI_xp4BfEBDRvCNHOUyMrL-unfatnVdbjFxXWMZRYUmt-h-NsHNCJaLksI-fAl_M86WZV4K7fp_-yh5aSS8TPe7xtslQ91_R1e8o8AFTq7FKm3CiQ9Ce5ZjQM-uIdCXQuNBlAmmRgcSjGTlmL7jTqOrfhD7sAXlwjIS9Tbwq9VbXQ9HnrACaX7yO9MesR00OSGNVrc2cqiqBzdkPScgDQKY-eMO1-9dANsATFfkht-C1eu6Yf9Z4sXb7Kc=w1674-h1832-no)
![](https://lh3.googleusercontent.com/EXKiyfOcfE5cMtsSL1kXfluOoi9Dv98Iw10LhOQWAeXNXoaeqROIPgtapXefHsPJpE49rEjJCEvNBTQJ95w9MB8SSmfJapjps9-gRIbaIW66O1rq9ppUVUZE3Vr7IWp3L1i8qSg-RVaERC8NH43TmnuOltl9tDySisT52dXxROn1eUn--LocnFuGn0j5LT3Am0Hj6nmqmVSd9yvufHGmnPJX6IisbYDQ3RigdViTBrNS5pAbVxIvTENZYqSOiV1e0c_p4QxwxIuLcprV7lyFUQUcDmLWrCHfKFmw0djOvYMVa2qQptkjGSdAC8Q8ENX3q7wpTQb3_UJtBIOYLLkkKT-XZThcuELLqzn3O9fkc9XO0xMwN3abJTOXCe82-fhjqy3efC0GzSw1t8Te8-2fvLDG9tINccZEfG1lY6m2eW1dVkbvYZjwEMJ1oHQMvt_iTRyYF-ERYQ5RU1Ym1Pu8YBTlkvQGGY8UR0VkcKcygkOLQlhbx363DYF3x-7rFwZZu6MZEwQtvPaouHguTR84Z-vapZag8qB6e_q4ydsQsSzwblSX6s0f0tGUQZ2q4bhbTzsyVpj6M5eTh9t6deBuGQXryFwv-Cqjr2i47K1Lj5NtyLo9LC9iVOEvRjRchwvwaizcrpLLVN52iIMjItWgV6M=w2332-h1832-no)

## Monomorphisms and Simple Types

![](https://lh3.googleusercontent.com/QvCPbU2arwZPpiF-C6Txwk5q_gOUqM234XF_vw10k8gKfVWi8u9I3F5dCLkkn9I7YLeaO1J8svMbrrqD8e5yQ2i62BT2JXAna0vxqSQBFxADtAQb2H1ACBZzrZgYh_zdWCqypYqf7LcM1CY1HFd-Vk3Dqb05amJ4qlZRSRIZMZOLKRMc7getPrYuIFi9mtUhUyxi0mmoi-IVtTDm2YzCK4hjrDdVdGjutG-zqpNJg3DbLuvGILKaTFeHCuyjpvlsuNz4dDjuOQ7WnUYzpc1vnWGafIIMwv2t1BYSApnjlGE2V2JDpN8h1NCAteVF5j4Kgrt0WgxLiGNEHkX4DZ93mchEg07u-q1DfrJVtMflJOh4PmLUElEyROzy5Z9s49emE5QHP205qDgG-IAQu7OoN_v8VR-i08sNDwTj6viz6i-GUoYtg5wYKP9fpHC8Bfz8eq8driQ0-kwGCmhckyvWNdjlYrtZTMEoCceGfLS9W-w218V45SFWkNhTgAMIXmLpUUF6SapjmsImHy7qiPc71wUjh-tACuOgxl9M6ZAi13Yvq28oInCtgU_njhuSuoPCac6YD25tCqeEtudIHxzfro183WVIIkFNU0ODCErrYWzm1svQpeUTbczKbS8LYpDz08LY5mD-CPipshIqODMl3EQ=w1616-h1834-no)
![](https://lh3.googleusercontent.com/75nkAxGfzl4RaMyGHnprBYXZnW1XzdtEPDTdBW8zqgbP9xBxzTIPZe0SQomrEByEwn-qux8dbozhD_X82IevC9cPcLmFycmVfPxW_XymvSG_UTTQO5vMzKL-iDwgd3jQKHDuSfuLGkFtGQltla2Y_N9PObzAmbCt3ivEYoQ3fhnQoAdu4_jqAeP9DXLbh0lZ7B1eL2tTT8glBCaBBDiUSGcQo2BcfoUrRw5XP09Zd-XnuqqC3l4PTHFyNdH1oApdakwRvR6oyQOt9yCWHS4oZAVqnIKfB8E_UlA-SJfNnbr9izJuxpjI6HIC4vHdXwL7eYBIbVKvjyXjyeV_X91ZHCvVKzi79e2zI4aSIuoNGhENYDtN1wUP3X_mQIdkE3G84Z2E9IAeefXNQQAktbF8PaSHVFyBqN3JTmhfP8t9ZRFU-ylHToJfWQv2gR8dETqWSwSmkQ7--2T02lP5r7lkdDEKEshGRkZe-9YKdpjNaT5EItaXtMDF0q_HWWO6jFwAcpoKn-Z600J2YPWdlpdVKCtfg9hFdeJo5cC33CdMAyH9KeJj5qgKtHtrKPRV_sPmMEfTwfvbGfwAPU8PE1BxqarcHEzqnlq0uWIdbkU9tnHGGwtB9XHKL2wrIKkykXWKFyooIjDfcPPJ2kw514VCNDw=w2132-h1532-no)
