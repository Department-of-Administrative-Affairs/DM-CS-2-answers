# Question 2

## Part A

| Part | Min           | Max           |
|------|---------------|---------------|
| i    | max(N_R, N_s) | N_R + N_s     |
| ii   | 0             | N_R * N_S     |
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

![\color{#888}{
\begin{aligned}
T1(rID, h) &= \pi_{regionID, highT}(RT)\\
T2(rID\underline{, l)} &= \pi_{regionID, lowT}(RT)\\
T3(regionID) &= \pi_{rID}(T1 \bowtie_{h < highT} RT)\\
T4(regionID) &= \pi_{rID}(T2 \bowtie_{\underline{l > lowT}} RT)\\
T5(regionID) &= \pi_{regionID}(RT) - T3\\
T6(regionID) &= \pi_{regionID}(RT) - T4\\
Result(n) &= \pi_{name}(RT \bowtie (T5 \cup T6))\\
\end{aligned}}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Baligned%7D%0AT1%28rID%2C+h%29+%26%3D+%5Cpi_%7BregionID%2C+highT%7D%28RT%29%5C%5C%0AT2%28rID%5Cunderline%7B%2C+l%29%7D+%26%3D+%5Cpi_%7BregionID%2C+lowT%7D%28RT%29%5C%5C%0AT3%28regionID%29+%26%3D+%5Cpi_%7BrID%7D%28T1+%5Cbowtie_%7Bh+%3C+highT%7D+RT%29%5C%5C%0AT4%28regionID%29+%26%3D+%5Cpi_%7BrID%7D%28T2+%5Cbowtie_%7B%5Cunderline%7Bl+%3E+lowT%7D%7D+RT%29%5C%5C%0AT5%28regionID%29+%26%3D+%5Cpi_%7BregionID%7D%28RT%29+-+T3%5C%5C%0AT6%28regionID%29+%26%3D+%5Cpi_%7BregionID%7D%28RT%29+-+T4%5C%5C%0AResult%28n%29+%26%3D+%5Cpi_%7Bname%7D%28RT+%5Cbowtie+%28T5+%5Ccup+T6%29%29%5C%5C%0A%5Cend%7Baligned%7D%7D)

T1: renamed highT to h

T2: renamed lowT to l

T3: ID of any region for which a higher temperature region exists (all regions that are not the max)

T4: ID of any region for which a lower temperature region exists (all regions that are not the min)

T5: ID of region/s with no higher temperature (max temp)

T6: ID of region/s with no lower temperature (min temp)

Result: Name of the region/s with the highest temperature and region/s with the lowest temperature 
