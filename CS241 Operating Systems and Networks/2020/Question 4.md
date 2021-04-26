# Question 4

## Part A

### i

![\color{#888}{
\begin{align*}
N \times \frac{F + H}{R}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0AN+%5Ctimes+%5Cfrac%7BF+%2B+H%7D%7BR%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

### ii

![\color{#888}{
\begin{align*}
(N + P - 1) \times \frac{\frac{F}{P} + H}{R}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%28N+%2B+P+-+1%29+%5Ctimes+%5Cfrac%7B%5Cfrac%7BF%7D%7BP%7D+%2B+H%7D%7BR%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

Takes P \* transmission time to transfer P packets from source to first router. Then takes (N-1) \* transmission time to transfer P packets from the first router to the destination.

### iii

Simplifying both we have:

i) 

![\color{#888}{
\begin{align*}
N \times \frac{F}{R}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0AN+%5Ctimes+%5Cfrac%7BF%7D%7BR%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

ii)

![\color{#888}{
\begin{align*}
(N - 1) \times \frac{\frac{F}{P}}{R} + \frac{F}{R}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%28N+-+1%29+%5Ctimes+%5Cfrac%7B%5Cfrac%7BF%7D%7BP%7D%7D%7BR%7D+%2B+%5Cfrac%7BF%7D%7BR%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

Clear to see here that ii) is going to be lower.

### iv

Substitue in values to get:

![\color{#888}{
\begin{align*}
\frac{2500}{P} + 100P + 1025
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Cfrac%7B2500%7D%7BP%7D+%2B+100P+%2B+1025%0A%5Cend%7Balign%2A%7D%0A%7D)

Then differentiate and make equal to 0 to find the value of P to produce the minimum value:

![\color{#888}{
\begin{align*}
100 - \frac{2500}{P^2} &= 0 \\
\frac{2500}{P^2} &= 100 \\
P &= 5
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A100+-+%5Cfrac%7B2500%7D%7BP%5E2%7D+%26%3D+0+%5C%5C%0A%5Cfrac%7B2500%7D%7BP%5E2%7D+%26%3D+100+%5C%5C%0AP+%26%3D+5%0A%5Cend%7Balign%2A%7D%0A%7D)

## Part B

Each one will require the sum of RNN1 to RNNn for DNS lookup plus 2 \* RNN0 to create the TCP connection

### i

DNS_Lookup + RTT0 + RTT0 + 8 * RTT0 = DNS_Lookup + 18 * RTT0

### ii

DNS_Lookup + RTT0 + RTT0 + 2 * (2 * RTT0) = DNS_Lookup + 6 * RTT0

### iii

DNS_Lookup + RTT0 + RTT0 + RTT0 = DNS_Lookup + 3 * RTT0