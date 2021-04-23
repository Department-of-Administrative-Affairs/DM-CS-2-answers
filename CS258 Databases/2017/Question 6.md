# Question 6

## Part A

No-read-up: a user cannot read an object with higher security class that the user itself.

No-write-down: a user cannot write to an object with lower security class that the user itself. This is to stop data being moved from a higher class to a lower class.

## Part B

Not relevant

## Part C

Domain Relation Calculus: The free variables are attributes that range over the domain.

Tuple Relation Calculus: The free variables are typles that range over the relation.

They are equally expressive.

*Probably need some more detail here*

## Part D
```
{ e.Fname | EMPLOYEE(e) AND 
    (∃d)(DEPARTMENT(d) AND d.Dname = 'Economics' AND 
        (∀p)(PROJECT(p) AND p.Dnum = d.Dnum AND 
            (∃w)(WORKS_ON(w) AND w.Pno = p.Pno AND w.Essn=e.Ssn)))}
```