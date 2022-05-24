# Question 2
## Part a
**INNER JOIN** joins tuples of two relations on some condition. If this condition is not satisfied, neither tuple will be in the result.

**LEFT OUTER JOIN** joins tuples on two relations on some condition. If the condition is not satisfied, the tuple in the "left" (*first defined*) relation will be included, and the entries for the "right" relation will be NULL.

**CROSS JOIN** returns all pair-wise combinations between tuples in two relations (also known as the Cartesian Product).

## Part b
### i)
Note the car model ***starts*** with 'Audi'.
```SQL
SELECT DriverName FROM DRIVERS
	WHERE DriverID IN
	(
		SELECT DriverID 
			FROM CARUSERS NATURAL JOIN CARMODELS
		WHERE CarModel LIKE 'Audi%'
	);
```

```sql
SELECT DriverName FROM Drivers
    NATURAL JOIN
CARUSERS
    NATURAL JOIN
CARMODELS
    WHERE CardModel LIKE 'Audi%';
```

### ii)
At least.
```SQL
SELECT DISTINCT AreaID FROM DRIVERAREA
	GROUP BY (AreaID) HAVING COUNT(DriverID) >= 8;
```

### iii)
- Find length driven for each carID in BOOKINGS
- Filter CARMODELS by above

```sql
SELECT DISTINCT CarModel FROM CARMODELS
    INNER JOIN
BOOKING ON CardID = BCardID
    GROUP BY (CarModel, CarID) HAVING SUM(MILES) > 10000;
```

### iv)
- 'Share the ***use*** of at least one car', could imply only cars in BOOKINGS
- They mustn't share **any** areas
```SQL
SELECT DISTINCT C1.DriverID AS Driver1, C2.DriverID AS Driver2
    FROM CARUSERS C1 INNER JOIN CARUSERS C2
        ON C1.DriverID < C2.DriverID
    WHERE NOT EXISTS
    (
        SELECT DISTINCT AreaID FROM DRIVERAREA D1
            WHERE D1.DriverID = C1.DriverID
    )
    INTERSECT
    (
        SELECT DISTINCT AreaID FROM DRIVERAREA D2
            WHERE D2.DriverID = C2.DriverID
    )
    AND EXISTS
    (
        SELECT DISTINCT BCarID FROM BOOKINGS B2
        WHERE B2.DriverID = C1.DriverID
    )
    INTERSECT
    (
        SELECT DISTINCT BCarID FROM BOOKINGS B3
        WHERE B3.DriverID = C2.DriverID
    );
```

Alternative method:

```sql
SELECT DISTINCT CU1.DriverID as Driver1, CU2.DriverID as Driver2 FROM CARUSERS CU1
  CROSS JOIN
CARUSERS CU2
  WHERE CU1.DriverID < CU2.DriverID AND
  CU1.CarID = CU2.CarID AND
  NOT EXISTS (
    SELECT * FROM DriverArea DA1 
      INNER JOIN 
    DriverArea DA2 ON DA1.AreaID = DA2.AreaID
    WHERE DA1.DriverID = CU1.DriverID AND
    WHERE DA2.DriverID = CU2.DriverID);
```