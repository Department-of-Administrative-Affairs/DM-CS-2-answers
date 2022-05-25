# Question 3
## Part (a)
(definitions)

## Part (b)

NP:

- $k$<span style="font-variant:small-caps;">-Colour</span>: Given a $k$ colouring for the graph (Size $O(\log (k) \cdot n )$), checking if any edge in the graph is between two nodes of the same colour is done in $O(m)$ time.

- <span style="font-variant:small-caps;">Connectivity</span>: given a path between each pair of nodes (size $O(m\cdot n^2)$), check if each path is end-to-end connected in $O(m)$ time, 

P:
- $2$<span style="font-variant:small-caps;">-Colour</span> is in P: Assign colour 1 to an arbitrary node, then repeatedly assign all neighbours of colour 1 with colour 2, and vice versa ($O(m)$). If colours clash, then return false. If not all coloured (i.e. not connected), assign colour 1 to a new arbitrary uncoloursed node 

- $3$<span style="font-variant:small-caps;">-Colour</span> not in P: 3SAT reduces to it

- <span style="font-variant:small-caps;">Connectivity</span> in P: BFS in $O(n+m)$ time, if not all nodes reached then disconnected

## Part (c)

No - since there exists TMs that reject every input, and TMs that dont, the language is not the empty set or the set of all TMs, so by Rice's theorem is undecidable