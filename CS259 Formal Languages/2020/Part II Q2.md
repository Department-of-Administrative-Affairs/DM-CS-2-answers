# a 
> This might not be a full proof, but I believe it is conceptually correct. I think only the second half is in fact needed to prove this, but kept both for completion.

This requires equivalence between languages accepted by universal-NFAs (UNFAs) and Regular Languages: UNFA ⟺ RL.

**RL ⟹ UNFA**

Any Regular Language has a DFA 𝐷 = (𝑄, 𝛴, 𝑞₀, 𝐹, 𝛿) that precisely recognises it.  
This DFA can be redefined as an NFA 𝑁 = (𝑄, 𝛴, 𝑞₀, 𝐹, 𝛿') (trivially redefining the transition function 𝛿 to result in singletons instead of states 𝛿').  
As 𝑁 operates in an exactly equivalent way to 𝐷, only one possible run (accepting or otherwise) exists for input string x (as with DFAs).  
Therefore a UNFA 𝑈 = 𝑁 exists that is equivalent to 𝑁, as when only 1 possible run exists, both some run being accepting and all runs being accepting are equivalent.  
Therefore, any regular language has an equivalent UNFA, which accepts precisely the same language.

**UNFA ⟹ RL**

UNFA 𝑈 accepting string 𝑥  
⟺ 𝑈 only accepts string 𝑥 when all runs of U on 𝑥 are accepting  
⟺ ∀𝑟 : 𝑟 is an accepting run of U on 𝑥  
⟺ ¬(∃𝑟 : 𝑟 is not an accepting run of U on 𝑥)  
⟺ ¬(∃𝑟 : 𝑟 is an accepting run of U̅ on 𝑥)  
⟺ ¬(∃𝑟 : 𝑟 is an accepting run of U̅ on 𝑥)  
⟺ ¬(NFA 𝑁 = U̅ accepting x)  
⟺ N̅ accepting 𝑥.

As Regular Languages are closed under complementation and 𝑁 is an NFA (represents a regular language), 𝑈 must also represent a regular language.  
As we have proven both RL ⟹ UNFA and UNFA ⟹ RL, UNFA ⟺ RL, so UNFAs precisely recognise regular languages.

# b
L = {a<sup>n</sup>b<sup>n<sup>3</sup></sup>c<sup>n</sup> | n ≥ 0}  
Assume by contradiction that L is context-free.  
Let p be the pumping length given by the Pumping Lemma.  
Choose string s = a<sup>p</sup>b<sup>p<sup>3</sup></sup>c<sup>p</sup> ∈ L. |s| ≥ p.  
Take an arbitrary decomposition s = uvxyz where |vxy| ≤ p and |vy| > 0.  

**Case 1**:  
i. v,y ∈ a*  
ii. v,y ∈ b*  
iii. v,y ∈ c*

Here, uv<sup>0</sup>xy<sup>0</sup>z ∉ L, due to incorrect number of symbols.  

**Case 2**:  
i. v ∈ aa*bb* or y ∈ aa*bb*  
ii. v ∈ bb*cc* or y ∈ bb*cc*

Here, uv<sup>2</sup>xy<sup>2</sup>z ∉ L, due to incorrect ordering of symbols.

**Case 3**:  
i. v ∈ aa* and y ∈ bb*  
ii. v ∈ bb* and y ∈ cc*

Here, uv<sup>0</sup>xy<sup>0</sup>z ∉ L, since #a's ≠ #c's.

So, s cannot be pumped, which contradicts the Pumping Lemma. Hence, L is not context-free.

# c
If A and B are regular, then there exist NFA that accept them.

Augment the NFA accepting A by implementing a stack that pushes each symbol read in the input string as the NFA reads it.
This results in a PDA M that accepts A and fills the stack with each symbol of the input string.

Augment the NFA accepting B by implementing a stack that pops some symbol for each symbol read in the input string by the NFA.
This results in a PDA N that accepts strings in B of length equal to the number of symbols in the stack before any symbol in the input string is read.

Design a PDA that pushes $ onto the stack, executes M, executes N, then pops $ from the stack and accepts. This PDA accepts A ⊕ B.  
Hence, A ⊕ B is context-free.

# d
A TM R that decides L is defined by the following.  

R = "On input x:  
  1. Zig-zag across the tape to check whether each 'a' in the substring of a's has a 'b' to match in the corresponding
     position in the substring of b's that follow. If an 'a' follows a 'b', or no 'b' is present to match an 'a', reject.
     Cross off symbols as they are checked to keep track of which positions are matched.  
  2. Once all a's have been crossed off, check for remaining b's. If any remain, reject; otherwise, accept."

Claim: R halts on every input.  
Proof:

**Case 1**: input string is not of the form a*b*.  
Step 1. of R will ensure such strings are rejected by detecting an 'a' that follows a 'b'.
  
**Case 2**: #a's > #b's  
Step 1. of R makes sure that a 'b' exists to match each 'a', so these strings will be rejected.
  
**Case 3**: #a's < #b's  
Step 2. of R makes sure that no b's remain once all a's have been crossed off, so these strings will be rejected.
  
**Case 4**: #a's = #b's  
Step 2 of R says that, if all a's and b's are matched with none leftover, the string is accepted, so these strings will be accepted.

Hence, R halts on every input.
