## Cycle Detection

> Does there exist a cycle in a linked list?

***Solution 1:***
*$O(\mu + \lambda)$ time, $O(1)$ space*

Consider the linked list $x_1 \rightarrow x_2 \rightarrow \ldots\rightarrow x_n$, where some $x_i = x_j$. Let $\mu$ be the smallest such $i$. And let $\lambda$ be the period of this cycle, i.e. $\min_l (x_i = x_{i + l})$. Now, see that $x_i = x_{i + k\lambda}$; and in particular, $x_i = x_{2i}$.

```python
from collections import namedtuple

links = [1, 2, 3]

def is_cycle(
```

## Rotate an Array

> Rotate an array $k$ steps to the right.

***Solution 1:***
*$\Theta(n)$ time, $\Theta(1)$ space*

Swap indices 0 and $k \pmod 4$, such that we place index 0 correctly. But now index $k$ is in the wrong place: index 0 instead of $2k \pmod n$. 

Let 

However, it may be the case that gcd(k, n) > 0 in which case mk = 0 for some m < n. For example, with n = 10, k = 4, and permutation group notation starting we would swap (04826). We now repeat the same process starting at 1, filling in the gaps: (15937). Let t be the minimum m, then there will be n/t transpositions of size t. 

We can calculate this t with the extended Euclidean algorithm, but we can be lazy: Starting with index 0,  we count how many swaps it takes to return to 0. With t, we continue on the with the remaining transitions: (1…)(2…)…(t - 1…).

```python
```