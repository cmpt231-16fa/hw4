---
layout: page
title: "HW4 Solns: CMPT231"
subtitle: "Lecture 4, ch8,11"
ext-js: "https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_CHTML"
---

### HW4 Solutions (20pts)

+ (1a) *(2pts)* Demonstrate **counting sort** on *A*

  |   index |  0 |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  8 |  9 |
  |---------|----|----|----|----|----|----|----|----|----|----|
  |      A: | -- | 84 | 22 | 16 | 35 | 95 | 57 | 19 | 30 | -- |
  | census: |  0 |  2 |  1 |  2 |  0 |  1 |  0 |  0 |  1 |  1 |
  | census: |  0 |  2 |  3 |  5 |  5 |  6 |  6 |  6 |  7 |  8 |
  | output: | -- | 16 | 19 | 22 | 35 | 30 | 57 | 84 | 95 | -- |

+ (1b) *(1pt)* We see that counting sort is **stable** because it preserves
  the original order of equivalent values -- in this case, the pairs
  (16, 19) and (35, 30) stay in the same relative order.

+ (2) *(3pts)* Demonstrate **radix sort** on *A*,

  | dec |  84 |  22 |  16 |  35 |  95 |  57 |  19 |  30 |
  |-----|-----|-----|-----|-----|-----|-----|-----|-----|
  | oct | 124 | 026 | 020 | 043 | 137 | 071 | 023 | 036 |
  | LSD | 020 | 071 | 043 | 023 | 124 | 026 | 036 | 137 |
  | 2SD | 020 | 023 | 124 | 026 | 036 | 137 | 043 | 071 |
  | MSD | 020 | 023 | 026 | 036 | 043 | 071 | 124 | 137 |
  | dec |  16 |  19 |  22 |  30 |  35 |  57 |  84 |  95 |

+ (3) *(3pts)* Demonstrate **bucket sort** on *A*

  | bucket | 0.00 | 0.13 | 0.24 | 0.37 | 0.48 | 0.61 | 0.72 | 0.85 |
  |--------|------|------|------|------|------|------|------|------|
  | item   |  --  |  22  |  35  |  --  |  57  |  --  |  84  |  95  |
  |  --    |  --  |  16  |  30  |  --  |  --  |  --  |  --  |  --  |
  |  --    |  --  |  19  |  --  |  --  |  --  |  --  |  --  |  --  |

+ (4a) *(3pts)* Multiplication hash, A=0.3:

  |  key  |   5 |  12 |   3 |  15 |   7 |   1 |   4 |
  |-------|-----|-----|-----|-----|-----|-----|-----|
  | k\*A  | 1.5 | 3.6 | 0.9 | 4.5 | 2.1 | 0.3 | 1.2 |
  | frac  | 0.5 | 0.6 | 0.9 | 0.5 | 0.1 | 0.3 | 0.2 |
  | fr\*m | 3.5 | 4.2 | 6.3 | 3.5 | 0.7 | 2.1 | 1.4 |
  | floor |  3  |  4  |  6  |  3  |  0  |  2  |  1  |

  Result:

  | buckt |  0 |  1 |  2 |  3 |  4 |  5 |  6 |
  |-------|----|----|----|----|----|----|----|
  |  item |  7 |  4 |  1 |  5 | 12 | -- |  3 |
  |   --  | -- | -- | -- | 15 | -- | -- | -- |

+ (4b) *(4pts)* Double-hash with division and mult, A=0.3:

  |  key  |  5 | 12 |  3 | 15 |  7 |  1 |  4 |
  |-------|----|----|----|----|----|----|----|
  | h1(k) |  5 |  5 |  3 |  1 |  0 |  1 |  4 |
  | h2(k) |  3 |  4 |  6 |  3 |  0 |  2 |  1 |
  | colli |  0 |  1 |  0 |  0 |  0 |  5 |  2 |
  | buckt |  5 |  2 |  3 |  1 |  0 |  4 |  6 |

  Result:

  | buckt |  0 |  1 |  2 |  3 |  4 |  5 |  6 |
  |-------|----|----|----|----|----|----|----|
  |  item |  7 | 15 | 12 |  3 |  1 |  5 |  4 |

+ (5) *(4pts)* Universal hash property:

  Yes, this pool satisfies the universal hash property.

  Universal hash: \`forall k\_1 != k\_2 in U:
  P\_(h in H)( h(k\_1) = h(k\_2) ) <= 1/m\`

  Since there are only 4 hash functions in the pool (|H|=4),
  and the hash table also has only 4 entries (m=4),
  we need to show that for any pair of keys, there are at most
  |H|/m = 4/4 = 1 hash functions that collide them.

  The key space and hash pool are small enough that we can
  just exhaustively list out all the outputs and look for collisions:

  |    k  | 0 | 1 | 2 | 3 |
  |-------|---|---|---|---|
  | h1(k) | 0 | 1 | 2 | 3 |
  | h2(k) | 0 | 2 | 0 | 1 |
  | h3(k) | 0 | 3 | 1 | 0 |
  | h4(k) | 0 | 0 | 3 | 2 |

  We observe that \`h\_2\` collides at \`k\_1=0\` and \`k\_2=2\`,
  \`h\_3\` collides at 0 and 3, and \`h\_4\` collides at 0 and 1.

  These collision pairs are all different, so there is no pair of
  keys in U on which more than one hash function in the pool collides.

  This is a small example of a Carter-Wegman family of hashes
  \`{h\_i(k) = (i\*k mod p) mod m}\_(i=1)^(p-1)\`, where p is a prime
  &ge; m.  These families are in general only approximately universal;
  \`P\_(h in H)( h(k\_1) = h(k\_2) ) <= 2/m\`.
