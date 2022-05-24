# Question 4

## (a) [5 points] Let the initial vertex be b. What is the sequence of edge relaxations  that the algorithm performs? Draw a table showing the intermediate distance values of all the nodes after each relaxation of the edge ed.

Sequence of edge relaxations: ba, bc, be, ed, ad, dc

| edge relaxed | a | b | c | d | e |
|:---:|:---:|:---:|:---:|:---:|:---:|
|initial|+∞|0|+∞|+∞|+∞|
|ba|-2|||||
|bc|||4|||
|be|||||1|
|ed||||3||
|ad||||-1||
|dc|||0|||

## (b) [5 points] Let G = (V, E) be an undirected graph with weights w: E→R.  Let e ∈ E be an edge of maximum weight. Suppose T is a spanning tree of G that has the maximum weight among all spanning trees of G. Prove that, if e is the only edge of G with weight w(e), then T must contain e.

Assume T does not contain edge e and has weight W<sub>1</sub>. Add edge e to the tree. The tree will no longer be spanning due to cycle C created by adding edge e. Pick an edge p on this cycle C that is not e. Removing this edge p will return T to a spanning tree and will have weight larger than W since w<sub>p</sub> \< w<sub>e</sub>.

## (c) Not In Syllabus

## (d) [6 points] For the weighted graph G depicted below, with w, s, and t as shown and with uv=ab, draw the graphs G(2), G(4), and G(6).

G(2): edge added between a and b with weight 2

G(4): edge added between a and b with weight 4

G(6): edge added between a and b with weight 6

## (e) [6 points] For the example from part (d),  compute the values D(2), D(4), and D(6).

D(2) = 4 + 2 + 2 =8

D(4) = 8 + 2 = 10

D(6) = 8 + 2 = 10

## (f) [12 points] Give a polynomial-time algorithm that, given G, w, s, t, u, v, and a sequence of positive real numbers q1, . . . , qk, computes the values D(q1), . . . , D(qk). Justify the correctness of your algorithm and analyse its worst-case running time.For full credit, your algorithm should run in time O((|V|+|E|) log|V|+k).

*Haven't completed this one yet, but feel it has something to do with divide and conquer and finding the value of q that splits between paths that use the new edge and ones that don't.*