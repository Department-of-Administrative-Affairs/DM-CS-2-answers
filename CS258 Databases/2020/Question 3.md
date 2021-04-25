# Question 3
## Part A
```sql
SELECT Super_ssn
FROM EMPLOYEE E
GROUP BY Super_ssn
HAVING AVG(Salary) > (
    SELECT AVG(Salary)
    FROM EMPLOYEE F
    JOIN DEPT_LOCATIONS L
    ON F.Dno = L.Dnumber
    Where L.Dlocation = 'Leamington'
)
   
```
> Selects supervisors whose supervisees have an average salary:
>  - greater than the average salaries of:
>  - employees who:
>  - work for a department:
>  - that is in Leamington
>                     

## Part B
```sql
-- SSN and Salary of the Employee and the supervisor's supervisor
WITH SupSup AS (
    SELECT SupSup.Ssn AS SupSupSSN, SupSup.Salary AS SupSupSal,
           Emp.Ssn AS EmpSSN,       Emp.Salary AS EmpSal
    FROM Employee Emp 
        JOIN Employee Sup    ON Emp.Super_ssn = Sup.Ssn 
        JOIN Employee SupSup ON Sup.Super_ssn = SupSup.Ssn
)

SELECT EmpSal
FROM SupSup WHERE
WHERE SSSal > ANY (
    SELECT S.Salary FROM Employee E 
        JOIN Employee S ON E.Super_ssn = S.Ssn
)
```

```sql
SELECT e1.Salary FROM employee e1 
    INNER JOIN employee e2 ON e1.Super_ssn = e2.Ssn
    INNER JOIN employee e3 ON e2.Super_ssn = e3.Ssn 

    WHERE e3.salary > ANY (
        SELECT Salary FROM employee WHERE Ssn IN (
            SELECT DISTINCT Super_ssn FROM employee
        )
    ); 
```

> SupSup lists the employee’s supervisor’s supervisor with the employee
> 
> Filters SupSup for there being a supervisor with a lower salary than the supervisor’s supervisor
> 
> `WITH` is definitely unnecessary, it just organises the query a bit better
> 

## Part C
```sql
WITH MinSal AS (
    SELECT MIN(E.Salary)
    FROM Employee E 
        JOIN Works_On W ON E.Ssn = W.Essn
        JOIN Project P ON W.Pno = P.Pnumber
    WHERE E.Address LIKE '%London%' AND P.Pname = 'X'
)

SELECT E.Fname, E.Minit, E.Lname, E.Salary
FROM Employee E
WHERE Address NOT LIKE '%London%' AND E.Salary > (MinSal * 1.2)
```
> MinSal is the minimum salary of London employee’s working on X. 
> 
> Then use this to find employee’s outside London with >1.2x this minimum

## Part D

```sql
SELECT MIN(Salary) 
FROM (
    SELECT Salary 
    FROM employee 
    ORDER BY Salary 
    DESC LIMIT 3
);
```

Or:

```sql
SELECT Salary
FROM EMPLOYEE
ORDER BY Salary DESC
OFFSET 2
LIMIT 1
```

> Retrieves the salary of an employee with exactly 2 salaries higher than it


