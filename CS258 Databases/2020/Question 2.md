> CS258 Databases 2020 Paper here: [https://warwick.ac.uk/services/exampapers/cs/2020/20200113_cs258_exam.pdf](https://warwick.ac.uk/services/exampapers/cs/2020/20200113_cs258_exam.pdf)
> 2 Hours. Attempt 4 questions

# Question 2

## Part A

| Part | Min           | Max           |
|------|---------------|---------------|
| i    | min(N_R, N_s) | N_R + N_s     |
| ii   | 0             | max(N_R, N_S) |
| iii  | 0             | N_R           |
| iv   | N_R           | N_R           |
| v    | 0             | N_R           |

## Part B

| R | A | B | S | B | C |
|---|---|---|---|---|---|
|   | 1 | 1 |   | 1 | 3 |
|   | 2 | 2 |   |   |   |

| i | A | C | ii | A | C | iii | A | C |
|---|---|---|----|---|---|-----|---|---|
|   | 1 | 3 |    | 1 | 3 |     | 1 | 3 |
|   |   |   |    |   |   |     | 2 | 3 |

> Both i and ii filter R for B=1 first: i as it is joining on B, where B can only be 1; ii explicitly. iii does not filter by B before cross joining, so R where B ≠ 1 is allowed

## Part C
I believe this should read:
$$
\begin{aligned}
T1(rID, h) &= \pi_{regionID, highT}(RT)\\
T2(rID\underline{, l)} &= \pi_{regionID, lowT}(RT)\\
T3(regionID) &= \pi_{rID}(T1 \bowtie_{h < highT} RT)\\
T4(regionID) &= \pi_{rID}(T2 \bowtie_{\underline{l > lowT}} RT)\\
T5(regionID) &= \pi_{regionID}(RT) - T3\\
T6(regionID) &= \pi_{regionID}(RT) - T4\\
Result(n) &= \pi_{name}(RT \bowtie (T5 \cup T6))\\
\end{aligned}
$$

T1: renamed highT to $h$
T2: renamed low T to $l$
T3: ID of any region for which a higher temperature region exists (all regions that are not the max)
T3: ID of any region for which a lower temperature region exists (all regions that are not the min)
T5: ID of region with no higher temperature (max temp)
T6: ID of region with no lower temperature (min temp)
Result: Name of the region with the highest temperature and region with the lowest temperature 
