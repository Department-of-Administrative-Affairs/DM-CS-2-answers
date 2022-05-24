# Question 3

## Part A

π<sub>Fname, Address</sub> (σ<sub>Sex='Male'</sub> (EMPLOYEE))

## Part B

π<sub>Pname</sub> (PROJECT ⋈<sub>Dnum=Dnumber</sub> (σ<sub>Dlocation='Singapore'</sub> (DEPT_LOCATIONS)))

## Part C

T<sub>1</sub> ← π<sub>Dlocation</sub> (σ<sub>DNumber=1</sub> (DEPT_LOCATIONS))

T<sub>2</sub> ← (DEPT_LOCATIONS) ÷ (T<sub>1</sub>)

π<sub>Dname</sub>((T<sub>2</sub>) * (DEPARTMENT))

## Part D

E<sub>1</sub> ← (EMPLOYEE) ⋈<sub>Ssn = Essn</sub> (WORKS_ON)

E<sub>2</sub> ← (EMPLOYEE) ⋈<sub>Ssn = Essn</sub> (WORKS_ON)

OS ← π<sub>E<sub>1</sub>.Ssn, E<sub>2</sub>.Ssn</sub> ((E<sub>1</sub>) ⋈<sub>E<sub>1</sub>.Ssn \< E<sub>2</sub>.Ssn AND E<sub>1</sub>.Pno != E<sub>2</sub>.Pno</sub> (E<sub>2</sub>))

S ← π<sub>E<sub>1</sub>.Ssn, E<sub>2</sub>.Ssn</sub> ((E<sub>1</sub>) ⋈<sub>E<sub>1</sub>.Ssn \< E<sub>2</sub>.Ssn AND E<sub>1</sub>.Pno = E<sub>2</sub>.Pno</sub> (E<sub>2</sub>))

π<sub>Ssn1, Ssn2</sub> (ρ<sub>(Ssn1, Ssn2)</sub> (OS - S))