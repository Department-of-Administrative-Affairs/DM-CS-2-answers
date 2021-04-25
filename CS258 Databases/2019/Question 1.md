# Question 1

## Part A

The Pno attribute of WORKS_ON refers to the primary key of PROJECT (being Pnumber). Every tuple in WORKS_ON refers to a unique tuple in PROJECT.

## Part B

```sql
CREATE VIEW V AS
   SELECT A.Dnumber, A.MgrLname, B.AvgSalary FROM
      (SELECT Dnumber, Lname as MgrLname FROM
             DEPARTMENT 
          INNER JOIN 
             EMPLOYEE 
          ON Mgr_ssn = Ssn) A
      NATURAL JOIN
      (SELECT Dnumber, AVG(Salary)as AvgSalary FROM
             PROJECT 
          INNER JOIN 
             DEPARTMENT 
          ON Dnum = Dnumber
       GROUP BY Dnumber) B;
```

```sql
CREATE VIEW V AS 
    SELECT Dname, y.Lname, a.AvgSal FROM department d
        INNER JOIN 
    (
        SELECT Dno, AVG(Salary) as AvgSal
        FROM employees GROUP BY (Dno)
    ) a 
        ON d.Dnumber  = a.Dno
    INNER JOIN employee y 
        ON y.Ssn = d.Mgr_ssn;
```

## Part C

```sql
CREATE VIEW COLLEAGUES AS
    SELECT E1.Ssn, COUNT(E2.Ssn) FROM
        EMPLOYEE E1 LEFT OUTER JOIN EMPLOYEE E2
    ON NOT (E1.Ssn=E2.Ssn)
    WHERE NOT EXISTS
        (SELECT * FROM
            (SELECT Pno FROM
                (SELECT Pno FROM WORKS_ON WHERE Essn = E1.Ssn)
            EXCEPT
                (SELECT Pno FROM WORKS_ON WHERE Essn = E2.Ssn)
            ) THIS
            UNION
            (SELECT Pno FROM
                (SELECT Pno FROM WORKS_ON WHERE Essn = E2.Ssn)
            EXCEPT
                (SELECT Pno FROM WORKS_ON WHERE Essn = E1.Ssn)
            ) THAT);
```

## Part D

```sql
SELECT p.Pname, d.Dname, h.eCount, h.hours FROM project p
INNER JOIN 
(
    SELECT COUNT(Essn) as eCount, Pno, SUM(Hours) AS hours 
    FROM works_on GROUP BY (Pno) HAVING COUNT(Essn) > 1
) h ON h.Pno = p.Dnum
INNER JOIN department d ON p.Dnum = d.Dnumber;
```