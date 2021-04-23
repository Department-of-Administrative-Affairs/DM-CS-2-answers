# Question 5

## Part A

1NF - YES: assume attributes are atomic, there exists a key.

2NF - NO: We have a partial dependency on the key {A, C} -> {B}

3NF - NO: Because it's not in 2NF

Therefore this relation is in 2NF.

## Part B

R<sub>1</sub>(**A**, **C**, **E**) : to maintain referential integrity.

R<sub>2</sub>(**A**, **C**, B) : to remove the {A, C} -> {B} partial dependency.

R<sub>3</sub>(**C**, **E**, D) : to remove the {C, E} -> {D} partial dependency.

R<sub>4</sub>(**A**, **E**, F) : to remove the {A, E} -> {F} partial dependency.

R<sub>5</sub>(**F**, I) : to remove transitive dependency.

R<sub>6</sub>(**D**, G, H) : to remove transitive dependencies.