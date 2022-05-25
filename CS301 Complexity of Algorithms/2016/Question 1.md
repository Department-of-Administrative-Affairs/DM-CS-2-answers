# Question 1
## Part (a)
The TM specified by:

|                   | 0                          | 1                         | ☐                        |
|-------------------|----------------------------|---------------------------|---------------------------|
| q<sub>start</sub> | (q<sub>start</sub>, 0, R)  | (q<sub>start</sub>, 0, R) | (q<sub>start</sub>, 0, R) |
| q<sub>end</sub>   | -                          | -                         | -                         |

will never halt, as it will continue to write 0s onto the tape forever.


## Part (b)

Let $f : (G, k) \mapsto (G', |V|-k)$ where $G'$ is the complement graph of $G$.
$f$ is a Karp reduction from <span style="font-variant:small-caps;">Vertex-Cover</span> to <span style="font-variant:small-caps;">Clique</span>:

If there is a vertex cover $S \subset V$ of size at most $k$ in a graph $G$, then take $C$ the complement of that vertex cover $C=V \setminus S$, having size $|C|\geq |V|-k$. There can be no edges between the vertices in $C$, or $S$ would not cover them, so the subgraph $C'$ in the complement graph must have all internal edges, i.e. is  a clique size $\geq |V|-k$ 

## Part (c)
```
FOR v IN V
    FOR (v,u) IN E
        FOR (v,w) IN E
            IF (u,w) IN E THEN RETURN FALSE
RETURN TRUE
```
Is an algorithm for deciding this language in $O(nm^3)$ steps, where $n=|V|, m=|E|$
