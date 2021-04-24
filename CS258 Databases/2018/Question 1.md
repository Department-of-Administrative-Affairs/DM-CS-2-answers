# Question 1
## Part a
NULL is a special marker to indicate a value for an attribute is not availabe, not applicable or unknown.

When any value is compared with NULL, the truth value is UNKNOWN. This includes comparing NULL to NULL. To check if some data is NULL, you need to use: 
```sql
IS NULL
```

```sql
COALESCE()
```
Therefore if you are comparing data, and some data could be NULL, either you use the above operation in conjunction with your equivalence operator or you restructure your data/query.

## Part b
An attribute that is defined as a **primary key** has the following constraints:
- Data cannot be NULL (any attribute of the primary key cannot be NULL)
- Primary key must be unique from every other data in primary key
- Only one primary key per table

These constraints are necessary as the **primary key** is used to identify all tuples, so constraints are necessary so that every tuple can be *uniquely* identified.

## Part c

### i
```SQL
CREATE VIEW BDRIVERS AS
	SELECT BookingID, DriverName
		FROM BOOKINGS NATURAL JOIN DRIVERS;
```

### ii
```SQL
CREATE VIEW EFFICIENCY AS
	SELECT DriverID, BLocation, SUM(Fare) / SUM(Miles) AS FarePerMile
		FROM BOOKINGS
	GROUP BY (DriverID, BLocation);
```

### iii)
For each driver:
- Count all distinct locations driver has been to in area 4
- Count all distinct locations in area 4
- Check equal

```SQL
CREATE VIEW COVERAGE AS
	SELECT DriverName FROM DRIVERS D WHERE
	(
		SELECT COUNT(DISTINCT BLocation)
			FROM BOOKINGS NATURAL JOIN AREALOCATIONS
		WHERE DriverID = D.DriverID AND AreaID = 4
	)
	=
	(
		SELECT COUNT(Location) FROM AREALOCATIONS
			WHERE AreaID = 4
	);
```