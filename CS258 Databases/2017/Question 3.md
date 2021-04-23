# Question 3

## Part A

π<sub>Fname, Address</sub> (σ<sub>Sex='Male'</sub> (EMPLOYEE))

## Part B

π<sub>Pname</sub> (PROJECT ⋈<sub>Dnum=Dnumber</sub> (σ<sub>Dlocation='Singapore'</sub> (DEPT_LOCATIONS)))

## Part C

T<sub>1</sub> <- π<sub>Dlocation</sub> (σ<sub>DNumber=1</sub> (DEPT_LOCATIONS))

T<sub>2</sub> <- (DEPT_LOCATIONS) ÷ (T<sub>1</sub>)

π<sub>Dname</sub>((T<sub>2</sub>) * (DEPARTMENT))

## Part D

T<sub>1</sub> <- π<sub>Ssn</sub>(EMPLOYEE)

T<sub>2</sub> <- (p<sub>(Ssn1)</sub>T1)⋈<sub>Ssn1 < Ssn2</sub>(p<sub>(Ssn2)</sub>(T2))

T<sub>3</sub> <- ((T<sub>2</sub>)⋈<sub>Ssn1 = Essn</sub>(WORKS_ON))

T<sub>4</sub> <- ((T<sub>2</sub>)⋈<sub>Ssn2 = Essn</sub>(WORKS_ON))

