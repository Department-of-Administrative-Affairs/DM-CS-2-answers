# Question 2
## Part (a)
<span style="font-variant:small-caps;">Primes</span> is in coNP iff <span style="font-variant:small-caps;">Composites</span> is in NP, where the <span style="font-variant:small-caps;">Composites</span> is the language of natural numbers $n$ with a factor $1< a <n$.

A certificate for this language is a given factor $a$ of size at most $|n|$, and can be certified by dividing $n$ by $a$ and checking if the result is an integer

## Part (b)

- RP : The set of languages $L$ where there exists a TM that:
  - Rejects $w \notin L$ with probability $1$
  - Accepts $w \in L$ with probability $\geq1/2$
  - Either accepts or rejects in $T(|w|)$ steps for some polynomial $T(x)$
- coRP : The set of languages $L$ such that $\Omega \setminus L$ is in RP
- BPP : The set of languages $L$ where there exists a TM that:
  - Rejects $w \notin L$ with probability $>1/2$
  - Accepts $w \in L$ with probability $>1/2$
  - Either accepts or rejects in $T(|w|)$ steps for some polynomial $T(x)$

## Part (c)

Let $L \in RP$. Then, we must have a TM that accepts on $w \in L$ with probability $p \geq 1/2$ and rejects always on $w \notin L$, terminating in at most $T(|w|)$. Construct a new turing machine TM* that simulates the TM on the input given. If TM rejects on an input, run it again, repeating up to $|w|$ times. 

This will terminate in at most $|w|T(|w|)$ steps, so is polynomial time, rejects all $w \notin L$ with probability $1^{|w|}=1$, and rejects $w\in L$ iff a false negative occurs $|w|$ times, with probability $p^{|w|} \leq (1/2)^{|w|}$, thus accepting with probability $\geq 1 - (1/2)^{|w|}$, so $L \in RP^*$ for all $L\in RP$, so $RP\subseteq RP^*$

Let $L \in RP^*$. If $\epsilon \notin L$ then the condition (i) is stronger than the condition in RP, so $L\in RP$.
If $\epsilon \in L$ then we can add an edge case to TM* to accept $\epsilon$. In either case we have TM* a turing machine with the properties in RP, so $RP^* \subseteq RP$
So $RP^* = RP$