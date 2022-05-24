# Question 3

## (a) Not In Syllabus

## (b) Not In Syllabus

## (c) Not In Syllabus

## (d) Not In Syllabus

## (e) [4 points] Consider four sequences of integers: A: 0,0,1,1; B: 0,0,0,1; C: 0,1,1,1; D: 2,0,1,0. What is the length of the longest common subsequence of:

### (i) A and B
001, length of 3
### (ii) A and C
011, length of 3
### (iii) A, B and C
01, length of 2
### (iv) A, B, C and D
01, length of 2

## (f) [2 points] Draw a 4×4 table of integers in which the contents of the first, second, third, and fourth rows are the sequences A,B,C, and D from part (e).  Is this table flat?
| | | | |
|:---:|:---:|:---:|:---:|
| 0 | 0 | 1 | 1 |
| 0 | 0 | 0 | 1 |
| 0 | 1 | 1 | 1 |
| 2 | 0 | 1 | 0 |

Table is flat (let k = 2).

## (g) [12 points] Give a polynomial-time algorithm that, given an n×n flat table of integers, finds the length of the longest common subsequence of its n rows. Justify the correctness of your algorithm and prove that it runs in polynomial time.

*This is a modified version of @TehDragonGuy#9740's algorithm* 

**We are not entirely certain this is the correct answer, and missing a proof of correctness.**

```
Initialise 2D array myList with n elements (each inner list stores pairs [i, j] of the max sequence of 0,1...i 0s followed by j 1s);
For each row r=(0,1...n):
    count0 = 0;
    count1 = count number of 1s in row r;
    Store [0, count1] in list in myList[r] ;
    For element in row:
        If element = 0:
            count0 = count0 + 1;
            Store (count0, count1) in myList[r];
        If element = 1:
            count1 = count1 - 1;

maxLength = 0;
for k = 0 to n:
    tempMaxLen = inf;
    for l = 0 to n:
        try:
            temp = myList[l][k][0] + myList[l][k][1]
            if temp < tempMaxLen:
                tempMaxLen = temp;
        except:
            break out of both loops
    if tempMaxLen > maxLength:
        maxLength = tempMaxLen

return maxLength
```

*This is an alternative algorithm that will be able to return the subseqeunce itself (which is not required)*

```
divisionArray[n+1];
for i=0 -> n:
  divisionArray[i]={i, n-i};

// Looping through each row
for r=1 -> n:
  num0s = 0;
  num1s = count1sInRow(r);

  if (num0s <= divisionArray[0][0] AND num1s <= divisionArray[0][1]):
      divisionArray[0] = {num0s, num1s};
  else if (num0s >= divisionArray[0][0] AND num1s >= divisionArray[0][1]):
      // Do nothing, keep element of divisionArray
  else:
      divisionArray[0] = NULL;
  
  for d=1 -> n:
    if (F[r][d] == 0):
      num0s++;
    else if (F[r][d] == 1);
      num1s--;
    if (num0s <= divisionArray[d][0] AND num1s <= divisionArray[d][1]):
      divisionArray[d] = {num0s, num1s};
    else if (num0s >= divisionArray[d][0] AND num1s >= divisionArray[d][1]):
      // Do nothing, keep element of divisionArray
    else:
      divisionArray[d] = NULL;

// Getting the longest common subsequence.
max0s = 0;
max1s = 0;
for d=0 -> n:
  if (divisionArray[d][0] + divisionArray[d][1] > max0s + max1s):
    maxOs = divisionArray[d][0];
    max1s = divisionArray[d][1];

return '0'*max0s + '1'*max1s;
```

Both of these algorithms run in 0(n<sup>2</sup>) time.