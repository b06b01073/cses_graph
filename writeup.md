# Writeup

Solutions to some of the hard problems.

## Flight discount

Use Dijstra to solve two single source shortest path problems, one start from node `1` the other start from node `n`. Let's say `src[i]` is the shortest path from `1` to node `i` and `dst[i]` is the shortest path from `n` to node `i`.

We next iterate all edges $E$, for each edge $e$ the weight is denoted by $w_e$ and the end points connected by the edge are from $A_e$ to $B_e$.

Then, the answer is 

$min_{\{e \in E\}} \ srt[A_e] + dst[B_e] + \frac{w_e}{2}.$