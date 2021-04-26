# Question 2

## Part A

### i

No since only 4 allowed to sit down at the table meaning there will always be a chopstick spare for one philosopher to pick up.

### ii

No since you always pick up from the left first and drop the right chopstick first. This will cause those with two chopsticks to move around the table anticlockwise. Also the philosopher waiting to sit down will be the only one waiting so when a philosopher leaves the table, they will be guaranteed a place.

## Part B

### i

![\color{#888}{
\begin{align*}
\frac{2}{2.2} * 100 = 90.91\%
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Cfrac%7B2%7D%7B2.2%7D+%2A+100+%3D+90.91%5C%25%0A%5Cend%7Balign%2A%7D%0A%7D)

Each job executes for 2ms, then switches taking 0.2ms.

### ii

![\color{#888}{
\begin{align*}
\frac{2*10 + 10}{2.2 * 10 + 10.2} * 100 = 93.17\%
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Cfrac%7B2%2A10+%2B+10%7D%7B2.2+%2A+10+%2B+10.2%7D+%2A+100+%3D+93.17%5C%25%0A%5Cend%7Balign%2A%7D%0A%7D)

IO jobs will execute for 2ms then switch taking 0.2ms. CPU jobs will run for 10ms then switch taking 0.2ms.

## Part C

### i

Should draw a Gantt Chart but here is the order

P1, P2, P3, P5, P2, P4, P1

Waiting times (TurnaroundTime - CPU_BurstTime - ArrivalTime):

P1 = 36 - 10 - 0 = 26

P2 = 22 - 5 - 2 = 15

P3 = 11 - 7 - 4 = 0

P4 = 28 - 6 - 4 = 18

P5 = 19 - 8 - 6 = 5

Avg = 12.8

### ii

Here we assume that when a new process comes, the process queue gets adjusted in order of priority.

P1, P2, P3, P5, P2, P4, P1, P3, P5, P4, P1, P3, P5, P1

P1 = 36 - 10 - 0 = 26

P2 = 14 - 5 - 2 = 7

P3 = 33 - 7 - 4 = 22

P4 = 29 - 6 - 4 = 19

P5 = 35 - 8 - 6 = 21

Avg = 19