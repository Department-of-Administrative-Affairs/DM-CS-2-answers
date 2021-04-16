# Question 1

## Part A

```sql
SELECT DISTINCT guestName, guestAddress
FROM Guest G 
    JOIN Booking B USING (guestNo)
    JOIN Hotel H USING (hotelNo)
WHERE guestAddress LIKE '%London%' AND H.city = 'London'
ORDER BY guestName
```

> Technically this answer is unreliable as the address could be something like "1 London Road, Coventry", however, this is obviously how they want you to match it, and we don't have a better way

## Part B

```sql
SELECT G.guestNo
FROM Guest G, Booking B
WHERE G.guestNo = B.guestNo
    AND guestName LIKE 'Peter %'
    AND B.dateTo IS NULL
```

## Part C

```sql
SELECT guestNo
FROM (SELECT G.guestNo FROM Guest G WHERE guestName LIKE 'Peter %') 
    INTERSECT (SELECT B.guestNo FROM Booking B WHERE B.dateTo IS NULL)
```

## Part D

```sql
SELECT price, roomNo, guestName
FROM Room R JOIN Hotel H USING (hotelNo)
    LEFT JOIN (
	SELECT hotelNo, guestName 
        FROM Booking B JOIN Guest G USING (guestNo)
	WHERE CURDATE() BETWEEN B.dateFrom and B.dateTo
    ) A USING (hotelNo)
WHERE hotelName = 'Hilton Hotel'
```

> The inner query gets the hotel and guest of any current booking, the outer query filters by hotel and selects. `LEFT JOIN` so NULL if no booking current exists