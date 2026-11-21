# How often a fixed scan finds a Mertens crossing

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412107.svg)](https://doi.org/10.5281/zenodo.24412107)

This result is now maintained in [quadratic-mertens-first-crossings](https://github.com/leecrossley/quadratic-mertens-first-crossings/tree/main/results/yokoi-mertens-geometric-starts). This repository is archived and keeps its releases and DOI.

Choose starting points in advance, each a fixed multiple of the last. For almost all fields in Yokoi's real quadratic family, a positive fraction of the first $J$ starts detect a dip in the prime-ideal Mertens product, for $J$ up to a constant times $\sqrt{\log D}$. At a successful start $y$, averaging with weight $y/t$ gives a negative result both over the full future and over the single window from $y$ to the next start.

There are absolute constants $K>1$, $y_0$, $c>0$ and $\theta>0$. In every sufficiently large discriminant shell $(D/2,D]$, the proportion missing **all** windows on the grid $y_0,K y_0,K^2 y_0,\ldots$ ending by $X$ is $O(X^{-\theta})$, uniformly through $X=\exp(c\sqrt{\log D})$. This also bounds the proportion whose first actual crossing is at or beyond $X$. The constants are asymptotic and have not been computed.

The proof controls how often the omitted primes beyond a window can erase its signal. The same primes in the window enter both averages with exactly the same coefficient. That equality lets the argument certify two negative integrals at one start. The theorem permits exceptional fields and leaves the all-field polynomial question open. [Proof and stronger grid statement](PROOF.md) · [Earlier literature](PRIOR-WORK.md) · [Johnston's 2024 problem](https://arxiv.org/pdf/2407.03530#page=4)

## Checks

Run the following from the release directory with Python 3.10 or later.

~~~sh
shasum -a 256 -c SHA256SUMS
python3 -B check.py
~~~

The finite checks are exact rational illustrations of the common block, polynomial and overlapping tails. The proof does not rely on them. Three auxiliary inequalities have Lean checks. The distribution theorem is a written proof. For the Lean replay, set NOTE to the absolute release directory, then run the following from [the pinned Mathlib checkout](https://github.com/leanprover-community/mathlib4/tree/0df444a360eaa60ab8c11dca51a86af692955474) with the toolchain in this release.

~~~sh
lake env lean -R "$NOTE" "$NOTE/Grid.lean"
~~~

[Exact checks](evidence/check.txt) · [Lean axioms](evidence/lean.txt)
