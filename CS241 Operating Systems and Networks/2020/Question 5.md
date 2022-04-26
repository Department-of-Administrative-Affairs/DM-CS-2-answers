# Question 5

## Part A

110 - 90 = 20 bytes

In TCP, the acknowledgment number is the next expected, therefore ACK(90) will be sent.

## Part B

### i

Yes. Receiver may have sent ACK that has got lost, but still moved their window up. Sender will then restransmit that packet due to a timeout.

### ii

The receiver here should acknowledge the packet otherwise the sender will not move it's window on due to waiting to receive an acknoweldgment.

## Part C

### i

18 transmissions
1, 2, 3, 4, 5, 6, 7, 5, 6, 7, 8, 9, 7, 8, 9, 10, 9, 10

### ii 

12 transmissions
1, 2, 3, 4, 5, 6, 7, 5, 8, 9, 10, 9


## Part D

### i

1 RTT to create connection, and:
1, 2, 4, 8, 16, 32, 64 (7 RTT)

Therefore takes 8 RTT.

### ii

1 RTT + 1, 2, 4, 8, 16, 32, 64, 65, 66, 67, ..., 77

At 77 over 1MB could've been sent, therefore takes 21 RTT.
