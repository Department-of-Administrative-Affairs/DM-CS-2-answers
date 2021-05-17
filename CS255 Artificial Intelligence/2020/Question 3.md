# Question 3
## Part a
### i.
Insert it into the order after Action2 to achieve precondition c5 for Finish

### ii.
If Action3 was inserted after Start, since it produces ¬c3, that would conflict with Action2's precondition c3. Causal link Action1 --c3--> Action2 is threatened.

Solution is to **promote** Action3 to move it *after* Action2.

## Part b
Add the sensing action before Action2 to check whether the precondition c4 holds. Add some contingency plan for ¬c4 in case it is discovered to be False.

## Part c
**Action monitoring** involves checking the preconditions of only the next action to be performed. **Plan monitoring** involves checking *all* causal links are intact at the current time.

Here, **action monitoring** requires checking c3 and c4 as the preconditions of the next action, Action2. However, **plan monitoring** requires checking c3, c4 and c2 as all the causal links that have been established so far.

## Part d
Backtrack and try something else.

## Part e
### i.
Conflict set is {r1, r2, r4} as they all could be fired next.

### ii.
Conflict set is {r2, r5} as r4 is less specific, so specificity ignores it.

>Specificity fires the most specific rule first.

>Refractoriness allows each rule to fire only once on the same data.

### iii.
r2 will be chosen, as `b` was added before `c`.

>Recency fires the rules in the order which the data arrives in the knowledge base, using the most up-to-date information.

## Part f
**Abduction** involves making assumptions to explain observations.

**Default Reasoning** involves making assumptions of normality even if they might not be true.

It is easier to assume a default and not worry about doing some more expensive reasoning until the default assumption is found to be not true.

## Part g
| Rule fired | KB contents   |
|------------|---------------|
|1           |A,E            |
|4           |A,E,F,B        |
|2, 5        |A,E,F,B,C,D,G  |
|3           |A,E,F,B,C,D,G,Z|

>**Forward chaining** involves working from what you know (what is in the KB) and firing **all available rules** at each stage, until no more rules can be fired, at which point you check whether the goal has been achieved.
