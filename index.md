---
layout: page
title: "HW4: CMPT231"
subtitle: "Lecture 4, ch8,11"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

{% include policies.md %}

### HW4 (20pts) [(solutions)](solns)

Let A = `[ 84, 22, 16, 35, 95, 57, 19, 30 ]`.

1. (a) *(2pts)* Demonstrate **counting sort** on *A*,
  sorting on only the **first** digit of each number.
  + (b) *(1pt)* How does your result demonstrate that
  counting sort is a **stable** sort?

2. *(3pts)* Demonstrate **radix sort** on *A*,
  using *r=3*-bit digits (i.e., base 8)

3. *(3pts)* Demonstrate **bucket sort** on *A*,
  with each number divided by 100 to get it into the range [0,1).

4. Let K = `[ 5, 12, 3, 15, 7, 1, 4 ]` be a sequence of keys. <br/>
  Demonstrate (show as much work as you can) inserting these keys
  in order into a **hash table** of size 7, if the hash table uses:
  + (a) *(3pts)* Chaining, with multiplication hash and A=0.3
  + (b) *(4pts)* Open addressing, with double-hash: \`h\_1\` is division hash,
    and \`h\_2\` is multiplication hash with A=0.3

5. *(4pts)* Consider a small hash table of size m = 4,
  and key space U = \`bbb Z\_m\` = {0, 1, 2, 3}. <br/>
  Let H = \`{h\_i}\_(i=1)^4\` be a **pool** of hash functions:
  \`h\_i(k) = ((i\*k) mod 5) mod 4\`. <br/>
  Does the pool H satisfy the **universal hash** property?

