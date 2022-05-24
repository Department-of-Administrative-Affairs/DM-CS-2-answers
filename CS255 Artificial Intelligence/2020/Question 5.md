# Question 5
## Part a
**Off-policy learning** learns the value of an optimal policy, regardless of the cost or danger of exploring.

**On-policy learning** learns the actual value of the policy being followed.

## Part b
Increase the learning rate (alpha)

Use softmax with a higher initial temperature

Initialise Q-values higher to encourage exploration

## Part c
Q[s1, right] <-- 0 + .1(5 + .95\*0 - 0) = .5

Q[s2, left] <-- 0 + .1(8 + .95\*.5 - 0) = .8475

Q[s1, pause] <-- 0 + .1(10 + .95\*.5 - 0) = 1.0475

Q[s1, right] <-- .5 + .1(6 + .95\*0 - .5) = 1.05

## Part d
### i.
Q[Green, Buy] <-- 10 + .1(13 + .95\*12 - 10) = 11.44

### ii.
```
p = e^(12/.9) / (e^(12/.9) + e^(11.44/.9))
  = .6507
```
  
## Part e
### i.
Constraint graph shown in file `5e i.`

Note: Domains are exactly as specified {1,2,3,4} - no changes.

### ii. 
Domain consistent constraint graph shown in file `5e ii.`

>Domain consistency means removing impossible values for constraints relating to a **single variable**, such as C<3 or B!=3
>
### iii.
|Arc considered | Relation | Variable | Current domain | New domain |
|---------------|----------|----------|----------------|------------|
| AB | A != B | A | 1,2,3,4 | 1,2,3,4 |
| AC | A == C | A | 1,2,3,4 | 1,2 |
| BC | B != C | B | 1,2,4 | 1,2,4 |
| BA | B != A | B | 1,2,4 | 1,2,4 |
| CB | C != B | C | 1,2 | 1,2 |
| CA | C = A | C | 1,2 | 1,2 |
| CD | C < D | C | 1,2 | 1,2 |
| DC | D > C | D | 1,2,3,4 | 2,3,4 |

> According to my seminar tutor, domain consistency checks are **directional** and thus need to be done in both directions (hence 8 rows). Checking C<D only checks for changes to the domain of C, and not D.

Arc-consistent constraint graph shown in file `5e iii.`

### iv.
Domain split graphs shown in file `5e iv. (1)` and `5e iv. (2)`

C's domain is split so in one graph it has value `1` and in the other it has value `2`. Arc consistency is run again to find remaining possible values for other variables.

>Domain splitting involves splitting the domain of a variable to create several graphs, with that variable instantiated in a different way in each one.
