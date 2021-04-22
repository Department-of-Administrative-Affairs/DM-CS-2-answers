# Question 4
## Part A
A set of attribute and domain pairs

## Part B
The assumption states that what is not known to be true, is false. In relations, this translates to data not present in a relation to be taken as false.


## Part C
### i) 
K = { Firstname, Lastname, Age, FavouriteFood } is a potential superkey, but not a potential candiate key as it is not minimal ('Age' can be removed and K will remain a valid superkey).

Therefore, the sets of potential candiate keys and superkeys are not the same as K is included in the set of superkeys but not the set of candidate keys.

### ii)

K = { FoodName, Price } is the only valid key and is thus the only superkey and only candidate key.

Therefore, the sets are the same as both contain only K.

## Part D
### i)
{ D } as all other attributes are dependent on D (D -> (A,E), A -> B -> C). 

D must be included in any key of R (as it is not dependent on any other attribute), and is thus the only candidate key.

### ii)
{ A, B } as all other attributes are dependent on them (A -> C, BC -> E, B -> D).

Again, both A and B must be included in any key of R (as neither are dependent on any other attribute), and thus { A, B } is the only candidate key.

### iii)
{ B, D } : D -> E, B -> A, AD -> C.

{ B, C } : BC -> D -> E, B -> A.

{ B, E } : E -> D, B -> A, AD -> C.

B must be included in any key of R (as it is not dependent on any other attribute), and only C or D can be combined with B to determine all other attributes. Therefore, these two keys are the only candidate keys.
