# Question 4

## Part A

A key is a candidate key which uniquely identifies all tuples in a relation using a minimal subet of attributes (removal of an attribute results in no longer being a superkey). There can be multiple keys for a relation and usually one is picked to be the primary key.

## Part B

These are candidate keys for the given state, but may not hold for the relation when more data is added

{ Postcode }

{ Age, Firstname }

{ Age, Surname }

Other superkeys can be made by adding any number attribute to any of these candidate keys listed above.

## Part C

### i

No - Barbara and Bernard have the same age of 40 (tuples 1 and 2)

### ii

Yes - where two tuples have the same name, the surname is also the same

### iii

No - Barbara and Brenda both have the same surname of Taylor (tuples 1 and 3)

## Part D

X -> YZ

then since Z subset of YZ then YZ -> Z (trivial dependency)

by transitivity X -> YZ -> Z therefore X -> Z
