# Question 5
## Part A
All attributes are atomic, a primary key has been given, and it is assumed that all attribute domains are atomic, meaning FILMS is at least in 1NF.

However, Role is dependent on a proper subset of the primary key (CastMember -> Role), meaning FILMS is not in 2NF or greater (as any larger NF must also be in 2NF).

Therefore, FILMS is in 1NF.

## Part B
FILMSCAST(**FilmName**, **ReleaseYear**, **CastMember**, Pay)

FILMS(**FilmName**, **ReleaseYear**, AgeRating)
- (FilmName, ReleaseYear) -> AgeRating 

CAST(**CastMember**, Role)
- CastMember -> Role

RATING(**AgeRating**, Curfew)
- AgeRating -> Curfew

As establised in part a), this set of relations is in 1NF (with the primary key for each relation given in **bold**).

There are no attributes dependent on a proper subset of the primary key for any relation -> 2NF.

There are no transitive dependenices in any relation -> 3NF.

> This would most likely require more justification, but I'm unsure how to go about it.
