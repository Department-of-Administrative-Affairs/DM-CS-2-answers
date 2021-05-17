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
