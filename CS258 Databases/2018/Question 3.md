# Question 3
## Part a

π<sub>CarModel</sub> ((σ<sub>BLocation='WB'</sub>(BOOKINGS)) ⋈<sub>BCardID=CardID</sub> (CARMODELS))

## Part b
T1 <--  σ<sub>DriverAge >= 25 AND 35 >= DriverAge</sub> ( DRIVERS )

π<sub>Location</sub> ( T1 * DRIVERAREA * AREALOCATIONS )

## Part c

DO <-- π<sub>DriverID</sub>((CAROWNERS) * (CARUSERS))

DU <-- (π<sub>DriverID</sub>(DRIVERS)) - D0

ρ<sub> Owners</sub> ( π<sub>DriverName</sub>((DU) * (DRIVERS)))

## Part d
T1 <-- π<sub>AreaID</sub> ( DRIVERAREA )

π<sub>DriverName</sub> ( σ<sub>( T1 - (π<sub>AreaID</sub> ( σ<sub>DriverID=DRIVERS.DriverID</sub> )  ( DRIVERAREA )) = NULL</sub> ) ( DRIVERS )

Alternative solution:

T<sub>0</sub> \<-- π<sub>CardID</sub>((π<sub>CardID, AreaID</sub>(CARUSERS * DRIVERAREA)) ÷ (π<sub>AreaID</sub>AREALOCATION))

ownerIDs <-- π<sub>DriverID</sub>(T<sub>0</sub> * CAROWNERS)

π<sub>DriverName</sub>(ownerIDs * DRIVERS)