# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

A refresher on TCC and LCC is available in the [course notes](https://oscarlvp.github.io/vandv-classes/#cohesion-graph).

## Answer

Intuitively, a class where TCC and LCC are equal follows this rule: \
Methodes with at least one instance variable in common **must** share **all** of their used instance variable.

For clarity, lets not actual write a java class, but represent it in a more abstract way. \
`a`, `b`, `c` and `d` being instance variables, and the function `x1(a,b)` \
`x2(a)` is not allowed, `x2(a,b,c)` is not allowed, if `a` is used in `x2`, only `x2(a,b)` is. \
its also possible to have multiple "groups" of function sharing the usage of some variable, like \
`x3(c)`, `x4(c)` and `x5(c)` or `x6(d)`
