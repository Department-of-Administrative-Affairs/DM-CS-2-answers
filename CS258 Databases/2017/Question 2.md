# Question 2

## Part A

```sql
SELECT Dependent_name FROM DEPENDENT
    INNER JOIN
DEPARTMENT
    On Essn = Mgr_ssn;
    WHERE Dname='Education';
```

## Part B

```sql
SELECT Fname FROM EMPLOYEE
    WHERE Ssn NOT IN 
        (SELECT Mgr_ssn AS Ssn FROM DEPARTMENT);
```

## Part C

```sql
SELECT D.Dnumber FROM Employee E 
    JOIN
Department D 
    ON E.Dno = D.Dnumber
GROUP BY D.Dnumber
HAVING 
    COUNT(case Sex when "M" then 1 else 0 end) > COUNT (case Sex when "F" then 1 else 0 end);
```

Alternative not using `case`:

```sql
SELECT M.Dno FROM
        (SELECT Dno, COUNT(Ssn) AS mCount FROM DEPARTMENT
            LEFT OUTER JOIN
        EMPLOYEE ON Dno = Dnumber
            WHERE Sex = 'Male'
        GROUP BY (Dno)) M
    NATURAL JOIN
        (SELECT Dno, COUNT(Ssn) AS fCount FROM DEPARTMENT
            LEFT OUTER JOIN
        EMPLOYEE ON Dno = Dnumber
            WHERE Sex = 'Female'
        GROUP BY (Dno)) F
WHERE M.mCount > F.fCount;
```

## Part D

```sql
SELECT E.Lname FROM 
(SELECT E.Lname, E.Ssn, D.Dnumber DEPARTMENT D 
    JOIN
EMPLOYEE E ON D.Mgr_SSN = E.SSN) ED
    LEFT OUTER JOIN
DEPT_LOCATIONS L ON L.Dnumber = ED.Dnumber
    GROUP BY (ED.Ssn, E.Lname)
    ORDER BY COUNT(DISTINCT L.DLOCATION) DESC;
```

## Part E

```sql
SELECT Dnumber, SUM(CountSsn) FROM
    (SELECT P.Dnum, COUNT(Ssn) AS CountSsn FROM PROJECT P
        INNER JOIN
        (SELECT WO1.Essn, WO1.Pno FROM WORKS_ON WO1
            CROSS JOIN
        WOKRS_ON WO2
            ON WO1.Pno = WO2.Pno 
            WHERE WO1.Essn < WO2.Essn) WO
        ON P.Pnumber = WO.Pno) C
    RIGHT OUTER JOIN 
DEPARTMENT D
    ON C.Dnum = D.Dnumber
    GROUP BY (Dnumber);
```
