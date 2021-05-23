## a
L = {w ∈ {a,b}\* | the number of b's in w is a multiple of 5}  
The DFA that accepts L must have states that 'track' the number of b's in the string.  
It would need a state for each of:  
0 mod 5, 1 mod 5, 2 mod 5, 3 mod 5, and 4 mod 5 number of b's.  
This is the only way a DFA could remember what the current multiple of b's are.

## b
<img src="https://user-images.githubusercontent.com/64030210/119241292-4043e780-bb4d-11eb-96d6-987829794e4d.jpg" width=600>

## c
### i
<img src="https://user-images.githubusercontent.com/64030210/119241370-c3fdd400-bb4d-11eb-9002-a87983067e9e.jpg" width=600>

### ii
<img src="https://user-images.githubusercontent.com/64030210/119241350-9f096100-bb4d-11eb-8413-f21d55ad6f16.jpg" width=600>

## d
Consider <M,x>, an instance of MP.  
Define TM M<sub>x</sub> as follows.

M<sub>x</sub>(y)
1. Simulate M on x for |y|-1 steps.
2. If M accepts, accept.

Claim: <M,x> ∈ MP ⇔ <M<sub>x</sub>> ∈ L.  

Proof:  
(⇒) <M,x> ∈ MP  
⇒ M accepts x [**def. of MP**]  
⇒ ∃y ∈ Σ\*, M<sub>x</sub>(y) accepts in |y|-1 steps [**desc. of M<sub>x</sub>**]  
⇒ <M<sub>x</sub>> ∈ L. [**def. of L**]

(⇐) <M<sub>x</sub>> ∈ L  
Assume by contradiction that M does not accept x.  
⇒ ¬∃y ∈ Σ\*, M accepts x in |y|-1 steps  
⇒ ∀y ∈ Σ\*, M<sub>x</sub>(y) does not accept [**desc. of M<sub>x</sub>**]  
⇒ <M<sub>x</sub>> ∉ L [**def. of L**]  
⇒ M accepts x [**contradiction**]  
⇒ <M,x> ∈ MP. [**def. of MP**]

We've shown MP ≤<sub>m</sub> L, and we know that MP is undecidable; hence, L is also undecidable.
