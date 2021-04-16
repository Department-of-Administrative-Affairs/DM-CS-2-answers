# Question 4
## Part A
### i.
X → Y

Z → Y

> For all X = x₁, Y = y₁, same for X = x₂. Therefore X → Y. Same for Z 

### ii.
X → Y

Z → Y

> Unchanged

## Part B
### i.
> A → B → F
>
> AC → E, 
> 
> C → D → G → H
> 
> A <-> I
> 

R1 1NF:

> 1NF: key of AC and assumed atomic
> 
> not 2NF as e.g. B only depends on A and doesn’t require the full key AC
> 

R2 2NF:

> 1NF: key of A and assumed atomic
> 
> 2NF as A → B,F
> 
> But not 3NF as A → B → F is a transitive dependency 
> 

R3 BCNF: 

> 1NF: key of AD
> 
> 2NF No non-key elements or FDs
> 
> 3NF: Again, no non-key elements or FDs
> 
> BCNF: And again
> 

R4 2NF:

> key of C
> 
> 2NF as C → D → G → H
> 
> not 3NF as transitive dependency
> 

R5 1NF: 

> 1NF: key of A/I and C (A <-> I), pick AC arbitrarily; not 2NF as I not dependent on C
> 

### ii.
R1(**A,C**, E) 

R1’/5(**A**, B, I) 

R1''/4(**C**, D) 

R2(**B**, F) 

R3(**A,D**) 


R4’(**D**, G) 

R4'’(**G**, H)

Have to break I → A to form BCNF


## Part C
As A is a candidate key, A → B.

If B is not a candidate key, A → B → C breaks 3NF 

If B is a candidate key A → B → C conforms to 3NF and BCNF 


> 3NF is only when there are no X → A where X is not a candidate key (and in 2NF)
> 
> or there is no transitive FD from a (candidate-)key to a non-(candidate-)key attribute
> 
> Alternatively, all attributes in A and not X are in some candidate key
> 

## Part D
AB is not, as D is independent of them.

ABD is a candidate key, as both C and E are dependent on ABD and ABD is minimal.

## Part E
> R = {C, SN, OD, CH, CL, I, S, Y, D, RM, NS}
> 
> {C} → {OD, CH, CL}
> 
> {C, SN, S, Y} → {D, RM, NS, I}
> 
> {RM, D, S, Y} → {I, C, SN}
> 

Candidate keys: {C,S,Y,SN} and {C,S,Y,RM,D}

C, S and Y are included in all keys as they do not depend on anything, and including C fulfils the first FD.

Then either SN or {RM, D} must be included to fulfil the 2nd then 3rd FD, or 3rd then 2nd respectively. 



R = {**C, SN, S, Y**, OD, CH, CL, I, D, RM, NS}

Chosen key of C,S,Y,SN as shorter. All of these fields are assumed atomic.



Maintain relations to match FDs apart from repeated I

R1 = {**C**, OD, CH, CL}

R2 = {**C, SN, S, Y**, D, RM, NS}

R3 = {**RM, D, S, Y**, I, C, SN}

These all match requirements for 1,2,3 and BCNF, not sure what else is needed commenting on

