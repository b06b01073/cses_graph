# Writeup

Solutions to some of the hard problems.

## [Flight discount](https://cses.fi/problemset/task/1195)

Use Dijstra to solve two single source shortest path problems, one start from node `1` the other start from node `n`. Let's say `src[i]` is the shortest path from `1` to node `i` and `dst[i]` is the shortest path from `n` to node `i`.

We next iterate all edges $E$, for each edge $e$ the weight is denoted by $w_e$ and the end points connected by the edge are from $A_e$ to $B_e$.

Then, the answer is 

$$
min_{\{e \in E\}} \ src[A_e] + dst[B_e] + \frac{w_e}{2}.
$$

## [Flight routes check](https://cses.fi/problemset/task/1682/)
Quite an interesting question. It can be solved by Kosaraju's algorihtm, but it's an overkill, since we only need to know whether the graph is a **single** strongly connected component. We can use an interesting property, that is, **if every node can reach node $1$ and node $1$ can reach every other nodes, then the graph is strongly connected**. This can be proved with ease, given two vertices $v, u \in G$, we can always travel from $u$ to $v$ by first travel from $u$ to $1$, then from $1$ to $v$, therefore, $G$ is strongly connected.

Here, we only show that the condition is sufficient. The neccessity of the condition can also be proved easily. That is, we want to show that **if the graph is strongly connected, then every node can reach node $1$ and node $1$ can reach every other nodes**. This statement is automatically true by the definition of a strongly connected component. Therefore, the two conditions are equivalent.


#### Note: How to find whether every other nodes can reach node $1$?
reverse the graph and run dfs start from node $1$.
