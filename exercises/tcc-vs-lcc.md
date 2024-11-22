# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

A refresher on TCC and LCC is available in the [course notes](https://oscarlvp.github.io/vandv-classes/#cohesion-graph).

## Answer

Intuitively, a class where TCC and LCC are equal follows this rule: pairs of methode can not be (linked indirectly and not linked directly) in the graph. \
The constructed graph should be comprised only of fully interconnected clusters.

For clarity, lets not actual write the java class, but represent it in a more abstract way. \
with `a`, `b`, `c` and `d` being instance variables, and the functions `x1(a,b)` and `x2(c)` \
if `a` is used in `x3`, using `c` is not allowed, only a sub-group of [`a`,`b`,`d`], like `x3(a)` or `x3(a,d)`. Let's continue with `x3(a,b)` \
a methode `x4` using `c` could then be either `x4(c)` or `x4(c,d)`
