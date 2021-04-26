# Question 1

## Part A

### i

![\color{#888}{
\begin{align*}
2^{n+1} - 2
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A2%5E%7Bn%2B1%7D+-+2%0A%5Cend%7Balign%2A%7D%0A%7D)

### ii

![\color{#888}{
\begin{align*}
2^{n}
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A2%5E%7Bn%7D%0A%5Cend%7Balign%2A%7D%0A%7D)

## Part B

Where the OS is switching between jobs currently running on the CPU.

The OS will save the state of the currently running process to the PCB including the process' state, program counter and registers. The new process will then be loaded by using the PCB to load the registers and program counters and will change the state of the process to running.

## Part C

Code, Global Variables, Heap

## Part D

- One-to-one requires a kernel level thread per user level thread, whereas many-to-many allows you to specify the ratio of user level to kernel level threads
- Many-to-one has a reduced overhead since there are typically less kernel level threads created which can slow the system down in the case of one-to-one.

## Part E

![\color{#888}{
\begin{align*}
\frac{1}{0.6 + (0.5 * 0.3 * 0.4) + \frac{0.7 * 0.4}{4} + \frac{0.5 * 0.3 * 0.4}{2}} = 1.32 (2dp)
\end{align*}
}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ccolor%7B%23888%7D%7B%0A%5Cbegin%7Balign%2A%7D%0A%5Cfrac%7B1%7D%7B0.6+%2B+%280.5+%2A+0.3+%2A+0.4%29+%2B+%5Cfrac%7B0.7+%2A+0.4%7D%7B4%7D+%2B+%5Cfrac%7B0.5+%2A+0.3+%2A+0.4%7D%7B2%7D%7D+%3D+1.32+%282dp%29%0A%5Cend%7Balign%2A%7D%0A%7D)