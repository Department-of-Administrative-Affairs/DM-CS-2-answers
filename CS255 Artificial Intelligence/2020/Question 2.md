# Question 2
## Part a
### i.
Decision tree shown in file `2a i.`

### ii.
Do not take the bet. Expected loss of £6.

Shown on diagram by a filled in triangle after the decision node.

### iii.
Influence diagram shown in file `2a iii.`

### iv.
Added H node to influence diagram in file `2a iv.`

## Part b
### i.
f1(Run, Rain)

f2(Rain)

f3(Flooding, Blocked Drains, Rain)

f4(Blocked Drains)

f5(Bridge Closed, Flooding)

### ii.
We need to find `P(Blocked Drains | Bridge Closed, Run)`.  
Let event `E = Blocked Drains ∧ Bridge Closed ∧ Run`.  
`E` can be described by a set of possibilities:
```
{Blocked Drains ∧ Bridge Closed ∧ Run ∧ Flooding ∧ Rain,
 Blocked Drains ∧ Bridge Closed ∧ Run ∧ Flooding ∧ ¬Rain,
 Blocked Drains ∧ Bridge Closed ∧ Run ∧ ¬Flooding ∧ Rain,
 Blocked Drains ∧ Bridge Closed ∧ Run ∧ ¬Flooding ∧ ¬Rain}
```
`P(E)` is equal to the sum of the probabilities of the above possibilities.
```
P(Blocked Drains ∧ Bridge Closed ∧ Run ∧ Flooding ∧ Rain)
  = P(Blocked Drains) x P(Bridge Closed | Flooding) x P(Run | Rain) x P(Flooding | Rain, Blocked Drains) x P(Rain)
  = .3 x .8 x .2 x .8 x .4
  = .01536
  
P(Blocked Drains ∧ Bridge Closed ∧ Run ∧ Flooding ∧ ¬Rain)
  = P(Blocked Drains) x P(Bridge Closed | Flooding) x P(Run | ¬Rain) x P(Flooding | ¬Rain, Blocked Drains) x P(¬Rain)
  = .3 x .8 x .7 x .5 x .6
  = .0504
  
P(Blocked Drains ∧ Bridge Closed ∧ Run ∧ ¬Flooding ∧ Rain)
  = P(Blocked Drains) x P(Bridge Closed | ¬Flooding) x P(Run | Rain) x P(¬Flooding | Rain, Blocked Drains) x P(Rain)
  = .3 x .1 x .2 x .2 x .4
  = .00048
  
P(Blocked Drains ∧ Bridge Closed ∧ Run ∧ ¬Flooding ∧ ¬Rain)
  = P(Blocked Drains) x P(Bridge Closed | ¬Flooding) x P(Run | ¬Rain) x P(¬Flooding | ¬Rain, Blocked Drains) x P(¬Rain)
  = .3 x .1 x .7 x .5 x .6
  = .0063
```
Hence:
```
P(Blocked Drains | Bridge Closed, Run)
  = P(E)
  = .01536 + .0504 + .00048 + .0063
  = .07254
```
