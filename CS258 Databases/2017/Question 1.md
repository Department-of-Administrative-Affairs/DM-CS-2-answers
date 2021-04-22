# Question 4

## Part A

DEPENDENT(Essn, DependentName, Sex, Bdate, Realtionship)

Two tuples that violate key constraint:

T<sub>1</sub>(1, 'Harry', Male, 01/01/05, 'Brother')

T<sub>2</sub>(1, 'Harry', Male, 02/04/85, 'Father')

## Part B

WORKS_ON(Essn, Pno, Hours)

T<sub>1</sub>(1, 3, 10)

PROJECT(Pname, Pnumber, Plocation, Dnum)

T<sub>2</sub>('A Project', 1, 'London', 5)

Here T<sub>1</sub> references a project number of 3 which doesn't exist in the PROJECT table.

## Part C

### i

```sql
CREATE VIEW FMAN AS
    SELECT Fname FROM DEPARTMENT
        INNER JOIN
    EMPLOYEE
        ON Ssn = Mgr_ssn;
```

### ii

```sql
CREATE VIEW DEPRO AS
    SELECT Dnumber, Dname, COUNT(Pnumber) FROM DEPARTMENT
        LEFT OUTER JOIN
    PROJECT
        ON Dnumber = Dnum
    GROUP BY (Dnumber, Dname);
```

### iii

```sql
CREATE VIEW EMPNOT AS
    SELECT Dnumber, COUNT(E.Ssn) FROM DEPARTMENT D
        CROSS JOIN
    EMPLOYEE E
        WHERE NOT EXISTS
            (
                SELECT * FROM
                    (SELECT Pno FROM WORKS_ON WHERE Essn = E.Ssn)
                        UNION
                    (SELECT Pnumber AS Pno FROM PROJECT
                        INNER JOIN
                    DEPARTMENT 
                        ON Dnum = Dnumber
                    WHERE Dnumber = D.Dnumber)
            )
    GROUP BY (Dnumber);
```

This query used the `EXISTS` clause to allow us to use a subquery using the outer EMPLOYEE and DEPARTMENT attributes.