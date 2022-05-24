# Question 4

## Part A

A key is a set of attributes that are used to minimally identify a unique tuple (also know as a Candidate Key).

*Not sure since don't know what key means*

## Part B

Only superkey is {Name, Points, Town}

All the other possible combinations of attributes have values who don't uniquely identify the attributes not in the combination of attributes.

## Part C

Any subset of attributes of size 2. 

Size of 1 would not satisfy FDs.

Size of 3 would not be minimal.

## Part D

If FD doesn't hold, then the query will produce results. If FD does hold, then the query will not return results.

```sql
SELECT R1.Y, R2.Y FROM
R R1 INNER JOIN R R2 ON R1.X = R2.X
WHERE NOT (R1.Y = R2.Y);
```
