# Question 1
## Part a
### i.
Intercausal reasoning, since we know a cause and its effect but can reason about other possible causes.

### ii.
Diagnostic reasoning

## Part b
### i.
Probabilities we know:
`P(shower)=.1, P(OB|shower)=.82, P(OB|¬shower)=.12, P(NN|shower)=.88, P(NN|¬shower)=.15`

To find `P(shower|OB)` we use Bayes' rule:
`P(shower|OB)= (P(OB|shower) x P(shower)) / P(OB)`

> Bayes' Rule says P(A|B) = (P(B|A) x P(A)) / P(B)

We can find `P(OB)` by enumerating all the scenarios in which it occurs:

```
P(OB) = P(OB|shower)P(shower) + P(OB|¬shower)P(¬shower)
      = .82 x .1 + .12 x .9
      = .19
```

We then have all we need to find `P(shower|OB)`:

```
P(shower|OB) = (.82 x .1) / .19
             = .43158
```

The same logic holds for finding `P(shower|NN)`:

```
P(shower|NN) = (P(NN|shower) x P(shower)) / P(NN)
P(NN) = P(NN|shower)P(shower) + P(XX|¬shower)P(¬shower)
      = .88 x .1 + .15 x .9
      = .223

P(shower|NN) = (.88 x .1) / .223
             = .39462
```
Since 0.43158 > 0.39462 the **observatory** is a more reliable indicator

### ii.
We need to determine which prediction is more likely to be correct, i.e., `P(¬shower|¬NN)` vs. `P(shower|OB)`.
Using Baye's rule:
```
P(¬shower|¬NN) = (.85 x .9) / (.85 x .9 + .12 x .1)
               = .98456
```
Since `P(¬shower|¬NN)` > `P(shower|OB)`, the scientist shouldn't expect a meteor shower.


## Part c
### i.
SNOW  ---> ICY ROAD ---> ACCIDENT

|   |      | |    | S | ¬S  | |    |  I | ¬I |
|---|------|-|----|---|-----|-|----|----|----|
| S | .3   | |  I |.7 | .4  | |  A | .6 | .5 |
|¬S | .7   | | ¬I |.3 | .6  | | ¬A | .4 | .5 |
      
>Diagram has each event in a bubble with its probability table next to it

### ii.
Using Baye's rule:
```
P(S|A) = (P(A|S) x P(S)) / P(A)
```
To calculate `P(A)`:
```
P(A) = P(S) x P(A|S) + P(¬S) x P(A|¬S)
```
We need `P(A|S)` and `P(A|¬S)`. S and A are conditionally independent, since the BBN obeys the Markov condition and neither S nor A are parents/children of each other.
Using Chain rule:
```
P(A|S) = P(A|I) x P(I|S) + P(A|¬I) x P(¬I|S)
       = .6 x .7 + .5 x .3
       = .57

P(A|¬S) = P(A|I) x P(I|¬S) + P(A|¬I) x P(¬I|¬S)
        = .6 x .4 + .5 x .6
        = .54
```
Hence, for `P(A)`:
```
P(A) = .3 x .57 + .7 x .54
     = .549
```
Therefore, `P(S|A)`:
```
P(S|A) = (.57 x .3) / .549
       = .31148
```

## Part d
To find the probability of one event occurring regardless of the others, you can sum together all values for which it is True or False and use them collectively.

e.g. to determine `P(Asthma)` regardless of Smoking or Allergies, sum `0.1`,`0.2`,`0.05` and `0.25` to get `0.6`
