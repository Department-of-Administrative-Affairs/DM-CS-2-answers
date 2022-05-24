# Question 2

## Part A

```sql
SELECT Bdate FROM 
   DEPARTMENT INNER JOIN EMPLOYEE ON Ssn = Mgr_ssn
WHERE Dnumber = 6;
```

## Part B

```sql
SELECT Fname, Lname FROM
   EMPLOYEE
WHERE Salary >
   (SELECT Salary FROM 
       DEPARTMENT INNER JOIN EMPLOYEE ON Ssn = Mgr_ssn
    WHERE Dnumber = 5);
```
## Part C

```sql
SELECT Pnumber FROM PROJECT
    WHERE Pnumber NOT IN
        (SELECT Pno FROM WORKS_ON 
            INNER JOIN 
        EMPLOYEE ON Ssn = Essn
            WHERE NOT (Minit='A.'));
```

## Part D

```sql
SELECT Dno, DM.NumMale FROM
    (SELECT Dno, COUNT(Ssn) AS NumMale FROM EMPLOYEE WHERE Sex='Male' GROUP BY (Dno)) DM
NATURAL JOIN
    (SELECT Dno, COUNT(Ssn) AS NumFemale FROM EMPLOYEE WHERE Sex='Female' GROUP BY (Dno)) DF
WHERE DM.NumMale > 0 AND DF.NumFemale = 0;
```

Alternative using case:

```sql
SELECT Dno, Count(E.Ssn) FROM EMPLOYEE E 
    GROUP BY Dno
        HAVING COUNT(case Sex when "F" then 1 else 0 end) = 0 
        AND COUNT(case Sex when "M" then 1 else 0 end) >= 1;
```