# Question 4
## Part a
### i.
> Lowest-cost-first graph search orders the frontier based on the cost to reach a node so far.

|Frontier|Closed set|Pruned|Expanded|
|--------|----------|------|--------|
| \<A\>0           |-         |-     |-       |
| \<AB\>1          |A         |-     |\<A\>       |
| \<ABC\>3          |AB        |-     |\<AB\>       |
| \<ABCD\>5          |ABC        |-     |\<ABC\>       |
| \<ABCDG\>7, \<ABCDF\>8, \<ABCDE\>9  |ABCD |\<ABCDB\> |\<ABCD\> |
| \<ABCDF\>8, \<ABCDE\>9, \<ABCDGH\>16  |ABCDG |- |\<ABCDG\> |
| \<ABCDE\>9, \<ABCDFH\>11, \<ABCDGH\>16  |ABCDGF |\<ABCDFD\> |\<ABCDF\> |
| \<ABCDFH\>11, \<ABCDEH\>15, \<ABCDGH\>16  |ABCDGFE |\<ABCDEF\> |\<ABCDE\> |
| \<ABCDEH\>15, \<ABCDGH\>16  |ABCDGFEH |- |\<ABCDFH\> |

H is reached. Path: `ABCDFH`. Path cost: `11`. Expanded `8` paths.

> Paths are pruned when a node in the closed list is visited again.

### ii.
>Greedy best-first graph search orders the frontier by the heuristic value of the last node.

|Frontier|Closed set|Pruned|Expanded|
|--------|----------|------|--------|
| \<A\>10           |-         |-     |-         |
| \<AB\>9           |A         |-     |\<A\>     |
| \<ABC\>8          |AB        |-     |\<AB\>    |
| \<ABCD\>6         |ABC       |-     |\<ABC\>   |
| \<ABCDG\>1, \<ABCDF\>2, \<ABCDE\>6 |ABCD |\<ABCDB\>     |\<ABCD\>       |
| \<ABCDGH\>0, \<ABCDF\>2, \<ABCDE\>6 |ABCDG |-     |\<ABCDG\>       |
| \<ABCDF\>2, \<ABCDE\>6 |ABCDGH |-     |\<ABCDGH\>       |

H is reached. Path: `ABCDGH`. Path cost: `16`. Expanded `6` paths.

### iii.
>A* graph search orderes the frontier by (cost to reach node + heuristic of node).

|Frontier|Closed set|Pruned|Expanded|
|--------|----------|------|--------|
| **\<A\>**(0+10=10)   |-         |-     |-         |
| **\<AB\>**(1+9=10)   |A         |-     |\<A\>     |
| **\<ABC\>**(3+8=11)  |AB        |-     |\<AB\>    |
| **\<ABCD\>**(5+6=11) |ABC       |-     |\<ABC\>   |
| **\<ABCDG\>**(7+1=8), **\<ABCDF\>**(8+2=10), **\<ABCDE\>**(9+6=15) |ABCD      |\<ABCDB\>     |\<ABCD\>   |
| **\<ABCDF\>**(10), **\<ABCDE\>**(15), **\<ABCDGH\>**(16+0=16)   |ABCDG         |-             |\<ABCDG\>   |
| **\<ABCDFH\>**(11+0=11), **\<ABCDE\>**(15), **\<ABCDGH\>**(16)  |ABCDGF       |\<ABCDFD\>    |\<ABCDF\>   |
| **\<ABCDE\>**(15), **\<ABCDGH\>**(16)                       |ABCDGFH       |-             |\<ABCDFH\>   |

H is reached. Path: `ABCDFH`. Path cost: `11`. Expanded `7` paths.

## Part b
Construct a table of shortest paths from each node to G. Initialise H to 0 and all other nodes to infinity.

While all nodes have not been reached:

Travel along edges in opposite direction to arrows.

If travelling back along an edge from `u` to `v` with weight `x`, and `Entry(v)+x < Entry(u)`, set `Entry(u)` to `Entry(v)+x`

## Part c
H2 is the best as it will be closest to the actual cost, without going over, as h1...hn are all also underestimates.

>An admissible heuristic is one that is always an **underestimate** of the actual cost path to a node

H1 is admissible as `mean(h1...hn)` is always less than or equal to `max(h1...hn)` for any h.

H3 is NOT always admissible as the sum of all the heuristics is likely to be greater than the actual distance, thus making the sum an *overestimate*.

## Part d
Remove any nodes you encounter which are already on the path. For example, `\<SABCDA\>` will be pruned at depth 6, because `A` is already on the path.

Time needed is O(|p|) where |p| is the length of each new path, as every new path added must be checked in its entirety.
