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
Q[Green, Buy] <-- 10 + .1(13 + .95\*18 - 10) = 12.01

### ii.
`p = e^(12/.9) / (e^(12/.9) + e^(12.06/.9))`
`  = .4833`
  
## Part e
### i.

### ii. 
