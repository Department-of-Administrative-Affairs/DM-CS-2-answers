# Question 3

## Part A

π<sub>Ssn</sub>(σ<sub>Fname="Graham"</sub>(EMPLOYEE))

## Part B

AJB ← π<sub>Ssn</sub>(σ<sub>Fname='Alan' AND Minit='J.' AND Lname='Baker'</sub>(EMPLOYEE))

π<sub>Dependent_name</sub>((DEPENDENT)⨝<sub>Ssn=Essn</sub>(AJB))

## Part C

MGRD3 ← π<sub>Mgr_ssn</sub>(σ<sub>Dnumber=3</sub>(DEPARTMENT))

π<sub>Lname</sub>((EMPLOYEE)⨝<sub>Super_ssn=Mgr_ssn</sub>(MGRD3))

Or using a scalar value in where:

π<sub>Lname</sub>(σ<sub>Super_ssn=MGRD3</sub>(EMPLOYEE))

## Part D

PD1 ← ρ<sub>(Pno)</sub>(π<sub>Pnumber</sub>(σ<sub>Dnum=1</sub>(PROJECT)))

EWOP ← (π<sub>Essn, Pno</sub>(WORKS_ON))÷(PD1)

π<sub>Lname</sub>((EMPLOYEE)⨝<sub>Ssn=Essn</sub>(EWOP)

