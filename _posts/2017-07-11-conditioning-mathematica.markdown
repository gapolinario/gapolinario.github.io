---
layout: post
title:  "Conditioning Mathematica"
date:   2017-07-11 12:00:00 -0200
categories: mathematica
---

I was working on some combinatorics problem and Mathematica is always a good
guide in this type of problem, it can check your conjectured expressions
by making brute force combinations. Among other more subtle tricks. But today,
we talk about brute force.

First I'm going to expand a sum (this would be a good moment to have
latex or mathml configured for my blog, I know this day is going to come)

    t = Expand[Sum[s[i]s[i+1],{i,1,10}]^4]

This takes the fourth product of the sum, on a string of 10 spins,
expands and calls that s. Then I write out the following rule:

```
r = {s[_]^x_ :> x!! /; EvenQ[x], s[_]^x_ :> 0 /; OddQ[x], s[_] -> 0}
```

This is what it does: It reduces all even powers to a weird integral, then reduces all
odd powers to zero, which is the result of a weird but odd integral. The last rule
reduces s of anything to zero, this is the case of an odd power equal to one, which is
a special case. Then, the following application of the rule does magic

    t /. r

This only applies the rules when the expression satisfies a condition, which is having
an odd or even power.

This is still incomplete, but it came from problem 2 in <a href="http://www.if.ufrj.br/~moriconi//listsft/lista2.ps">this list</a>
on a statistical field theory course.
