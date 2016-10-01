---
layout: page
<<<<<<< HEAD
title: "HW4: CMPT231"
subtitle: "Lecture 4, ch8,11"
=======
title: "HW1: CMPT231"
subtitle: "Lecture 1, ch1-3"
>>>>>>> 8d732428b8c0fd7f89df4e5f89f3917ce343ce3d
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

<<<<<<< HEAD
### HW4 (20pts)
1. *(5pts)* 
=======
### HW1 (20pts) [(solutions)](solns)

1. *(4pts)* Demonstrate **insertion sort** on the following array of integers.
  Show as much work as you can.
  `[ 35, 50, 44, 61, 17, 75, 23, 9 ]`

2. *(4pts)* **Prove** from the definition of Theta:
  \` n^3 (2 + sin(n pi / 8)) + n^2 in Theta( n^3 ) \`

3. Consider the (pseudo)code given at the end of this question.
  + a. *(3pts)* Derive and simplify its **asymptotic complexity** T(n),
    in &Theta; notation, as a function of n.
  + b. *(1pt)* Is this function **polynomial** time, **exponential** time, or other?
  + c. *(1pts)* **Re-write** this function to run in O(1) time.
    You can use pseudocode, Python, whatever you like.

            def fib(n):
              if (n <= 0):
                return 0
              if (n == 1):
                return 1
              return fib(n-2) + fib(n-1)

4. Consider a group of n people.

  + a. *(2pts)* If each person needs to shake hands with every other person
    in the group exactly once, how many **hand shakes** will there be total?
    Compute exactly, as a function of n.

  + b. *(1pt)* Express (a) in &Theta; **asymptotic** notation.
    Is this linear, quadratic, exponential, or other?

  + c. *(3pt)* In 2011 [Facebook users had on average 190 friends](https://www.facebook.com/notes/facebook-data-science/anatomy-of-facebook/10150388519243859/).
    For each user in a group of n users, say you want to find that user's
    **oldest Facebook friend**; i.e., the person with which that user has
    been Facebook friends for the longest time.

    The **input** would be a list of n user IDs.
    The **output** should be a list of n user IDs, where the i-th user
    in the output is the oldest friend for the i-th user in the input.

    Discuss how you might **design** such a function,
    and what its **asymptotic complexity** would be, as a function of n.
    Is it linear, quadratic, exponential, or other?

  + d. *(1pt)* What's **different** about the situations in parts (b) and (c)
    that explains their different asymptotic complexities?

>>>>>>> 8d732428b8c0fd7f89df4e5f89f3917ce343ce3d
