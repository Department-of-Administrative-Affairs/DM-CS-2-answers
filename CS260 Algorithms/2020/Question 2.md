# Question 2
## (a) [4 points] For both of the following algorithms, specify what is given as input,what is the required output, and what is the worst-case running time: (i) Dijkstra’s algorithm, (ii) Bellman–Ford’s algorithm.

### (i) Dijkstra’s Algorithm
Input: Directed Graph G(V, E) with weights W where W<sub>e</sub> ≥ 0 for all e ∈ E, a source node s.

Output: Shortest path to all nodes from s.

Running Time: O(|V|<sup>2</sup>) with queue or array, O(|E|\*log(|V|)) with binary heaps.

### (ii) Bellman–Ford’s algorithm
Input: Directed Graph G(V, E) with weights W, a destination node t.

Output: Shortest path to t from all nodes.

Running Time: O(|V|\*|E|)

## (b) [8 points] Suppose a connected undirected weighted graph G= (V, E) with positive  weights has a unique minimum spanning  tree T. Is it true that the path between every two distinct vertices in T is always a shortest path between these vertices in G? Give a proof or a counterexample.

No. Consider a fully connected graph with nodes a, b, c with edge weights (a,b)=2, (a,c)=2, (b,c)=3. There is a unique MST using edes (a,b) and (a,c) with weight 4. But shortest path between b and c is edge (b,c) that is not included in the MST.

## (c) Not In Syllabus