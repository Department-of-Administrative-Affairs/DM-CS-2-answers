# Question 3

## Part A

No circular wait since a chain of resource requests cannot loop back on itself if you can only request the semaphores in ascending order of their number. Preventing circular wait ensures deadlock prevention.

## Part B

### i

True, if starvation cannot occur then this means no process is ever waiting indefinitely. A deadlock causes process/es to wait indefinitely.

### ii

False, for example take a system where there is a process that has the lowest priority and there is a constant stream of higher priority process. There isn't necessarily a deadlock here but the lower priority process will be starved.

### iii

True, deadlock prevention requires enforcing strict rules on how allocating and requesting recourses must be done.

### iv

False, the page tables are individual to each process and are generated based on what memory is allocated for the process.

## Part C

Consider case with resource type R with three instances and three processes. In this example a deadlock would occur:

P1 gets R1, P2 gets R2, P3 gets R3

P1 requests R2, P2 requests R3, P3 requests R1

## Part D

### i

P0, P3, P1, P2, P5

### ii

Yes, you can still do P0 then P3, then the allocation for P1 will be released after completing.

### iii

No, no process have all it's resources allocated.

## Part E

### i

![\color{#888}{
\begin{align*}
\log_{2}(4 * 1024) = 12
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Clog_%7B2%7D%284+%2A+1024%29+%3D+12%0A%5Cend%7Balign%2A%7D%0A%7D)

Therefore 12 bits for page offset

### ii

![\color{#888}{
\begin{align*}
32 - 12 = \text{ number of bits for page entries } = 10 \\
2^{16} \text{page entries}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A32+-+12+%3D+%5Ctext%7B+number+of+bits+for+page+entries+%7D+%3D+10+%5C%5C%0A2%5E%7B16%7D+%5Ctext%7Bpage+entries%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

### iii

![\color{#888}{
\begin{align*}
\frac{512MB}{4KB} = \frac{512 * 1024}{4} = 131072 = 2^{17}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Cfrac%7B512MB%7D%7B4KB%7D+%3D+%5Cfrac%7B512+%2A+1024%7D%7B4%7D+%3D+131072+%3D+2%5E%7B17%7D%0A%5Cend%7Balign%2A%7D%0A%7D)