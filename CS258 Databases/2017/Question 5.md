	a) Assuming atomicity of all attribute in 1nf
    Not in 2nd NF since {A,C} -> {B} and {A,C} is a proper subset of the primary key
    Not in 3rd NF since not in 2nd NF

	b) SECRETS(A, B, C, D, E, F, G, H, I)
    Remove dependencies on proper subsets for 2nd {A,C} -> {B}
    SECRETS(A,C,D,E,F,G,H,I)
    TABLEONE(A, C, B)
	
	Remove dependencies on proper subsets for 2nf and (3rd NF transitive dependencies)
	  {C,E}->{D} ({D}->{G}, {D}->{H}) 
	
    SECRETS(A,C,E,F,I)
    TABLEONE(A, C, B)
    TABLETWO(C, E, D, G, H)
	
	Remove dependencies on proper subsets for 2nf and (3rd NF transitive dependencies)
    {A, E}->{F} ({F}->{I}) 
	
    SECRETS(A,C,E,F,I)
    TABLEONE(A, C, B)
    TABLETWO(C, E, D, G, H)
    TABLETHREE(A, E, F, I)
	
Now in 3rd NF (I think)
