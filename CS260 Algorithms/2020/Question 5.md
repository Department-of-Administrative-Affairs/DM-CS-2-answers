# Question 5

## (a) [3 points] Give the definition of NP-hardness.

NP-Hardness is the class of problems that are at least as hard as the hardest problems in NP. A problem X is NP-hard if there exists an NP-complete problem Y that can be reduced to X.

## (b) [15 points] For each of the following statements, indicate whether it is true  or false. (Justification is not required. You will be awarded 3 points for each correct answer and−3 points for each incorrect or missing answer. Should the sum of the awarded points be negative, you will receive 0 points for this part of the question.)

(i) False

(ii) False

(iii) False

(iv) Not in Syllabus

(v) True

## (c) [8 points] Prove that the following Two Disjoint Paths problem belongs to the complexity class NP

Need to create poly-time algorithm that can verify the proof for Yes answers

```
for edge (u, v) in pathOne:
    for edge (i, j) in pathTwo:
        if (u == i OR u == j OR v == i OR v == j):
            return False;
return True
```

## (d) [8 points] Prove that the following Hitting Rows problem is NP-hard

To prove NP-hard, need to find an NP-complete problem that reduces to it.

Reducing Set Cover to Hitting Rows

```
SetCover(S, k):
    // S is an array containing each set.
    M = Matrix with row for each set, column for each element;
    for each set s in S:
        for each element e:
            if e in S:
                M[s][e] = 1;
            else:
                M[s][e] = 0;

    return HittingRows(M, k);
```

Since Set Cover is NP-complete, and we have produced a poly-time reduction to Hitting Rows, Hitting Rows must be NP-hard.

## (e) [6 points] Give a positive instance of the Hitting Rows problem with m = n = 3 and k = 2. Does there exist a negative instance of this problem with m = n = k = 3? Justify your answer.

*Not sure about this one since seems a bit trivial*

Positive instance m = n = 3 and k = 2

||||
|-|-|-|
|0|0|1|
|1|1|0|
|0|0|0|

Negative instance m = n = k = 3

||||
|-|-|-|
|0|0|1|
|1|0|0|
|1|0|0|