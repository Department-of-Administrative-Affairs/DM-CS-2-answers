# Question 3
## Part A
```sql
SELECT Super_ssn
FROM EMPLOYEE E
WHERE E.Salary > (
    SELECT AVG(E.Salary)
    FROM Employee E JOIN (
        SELECT W.Essn FROM WORKS_ON W 
        WHERE W.Pno IN 
            (SELECT Pnumber FROM Project
            WHERE Plocation = 'Leamington')
    ) T ON E.Ssn = T.ESsn
)
   
```
> As limited to 1 join only, use an `IN` instead. 
> Selects employees with salaries:
>     greater than the average salaries of:
>         employees who:
>             work on a project:
>                that is in Leamington

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
> SupSup lists the employee’s supervisor’s supervisor with the employee
> Filters SupSup for there being a supervisor with a lower salary than the supervisor’s supervisor
> `WITH` is definitely unnecessary, it just organises the query a bit better

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
> Then use this to find employee’s outside London with >1.2x this minimum

## Part D
```sql
SELECT DISTINCT E.Salary
FROM Employee E
WHERE 2 = (SELECT COUNT(DISTINCT(E2.Salary))
          FROM Employee E2 WHERE E2.Salary > E.Salary)
```
> Retrieves the salary of an employee with exactly 2 salaries higher than it


