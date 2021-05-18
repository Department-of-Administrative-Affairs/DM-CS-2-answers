# Question 2
## Part a
### i.
Decision tree shown in file `2a i.`

### ii.
Do not take the bet. Expected loss of £6.

Shown on diagram by a filled in triangle after the decision node.

### iii.
Influence diagram shown in file `2a iii.`

### iv.
Added H node to influence diagram in file `2a iv.`

## Part b
### i.
f<sub>1</sub>(Run, Rain)

f<sub>2</sub>(Rain)

f<sub>3</sub>(Flooding, Blocked Drains, Rain)

f<sub>4</sub>(Blocked Drains)

f<sub>5</sub>(Bridge Closed, Flooding)

### ii.
Note some shorthands: Flooding = F, Blocked Drains = BD, and Bridge Closed = BC.  
We need to find `P(BD|BC,Run)`.

**Step 1:** Set Run = T, BC = T, and remove from factors f<sub>1</sub> and f<sub>5</sub>, respectively.

f<sub>1</sub>(Rain):  
| Rain | val |
|------|-----|
| T    | .2  |
| F    | .7  |

f<sub>5</sub>(F):
| F | val |
|---|-----|
| T | .8  |
| F | .1  |

**Step 2:** Eliminate variables. Start by eliminating F.

f<sub>3</sub>(F, BD, Rain):  
| F | BD | Rain | val |
|---|----|------|-----|
| T | T  | T    | .8  |
| T | T  | F    | .5  |
| T | F  | T    | .6  |
| T | F  | F    | .2  |
| F | T  | T    | .2  |
| F | T  | F    | .5  |
| F | F  | T    | .4  |
| F | F  | F    | .8  |

Multiply all factors containing F.  
f<sub>3</sub> x f<sub>5</sub> = f<sub>3,5</sub>(F, BD, Rain):  
| F | BD | Rain | val  |
|---|----|------|------|
| T | T  | T    | .64  |
| T | T  | F    | .4   |
| T | F  | T    | .48  |
| T | F  | F    | .16  |
| F | T  | T    | .02  |
| F | T  | F    | .05  |
| F | F  | T    | .04  |
| F | F  | F    | .08  |

Sum F out.  
Σ<sub>F</sub> f<sub>3,5</sub> = f<sub>6</sub>(BD, Rain):  
| BD | Rain | val |
|----|------|-----|
| T  | T    | .66 |
| T  | F    | .45 |
| F  | T    | .52 |
| F  | F    | .24 |

Now we eliminate Rain.

f<sub>2</sub>(Rain):  
| Rain | val |
|------|-----|
| T    | .4  |
| F    | .6  |

Multiply all factors containing Rain.  
f<sub>1</sub> x f<sub>2</sub> x f<sub>6</sub> = f<sub>1,2,6</sub>(BD, Rain):  
| BD | Rain | val   |
|----|------|-------|
| T  | T    | .0528 |
| T  | F    | .189  |
| F  | T    | .0416 |
| F  | F    | .1008 |

Sum Rain out.  
Σ<sub>Rain</sub> f<sub>1,2,6</sub> = f<sub>7</sub>(BD):  
| BD | val   |
|----|-------|
| T  | .2418 |
| F  | .1424 |

**Step 3:** Multiply together factors containing BD.

f<sub>4</sub>(BD):  
| BD | val |
|----|-----|
| T  | .3  |
| F  | .7  |

f<sub>4</sub> x f<sub>7</sub> = f<sub>8</sub>(BD):  
| BD | val     |
|----|---------|
| T  | .07254  |
| F  | .09968  |

Finally:  
P(BD|BC,Run)  
= f<sub>8</sub>(BD) / Σ<sub>BD</sub> f<sub>8</sub>(BD)  
= .07254 / .07254 + .09968  
= .42121
