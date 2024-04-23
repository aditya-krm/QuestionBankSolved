## Bit-Stuffing Algorithms: Sender and Receiver

Here are two simple algorithms for bit-stuffing, one for the sender and one for the receiver:

**Algorithm 1: Sender (Bit Stuffing)**

This algorithm adds a '0' bit after every sequence of five consecutive '1' bits in the data stream.

```
1. Initialize a counter to 0.
2. For each bit in the data stream:
    a. If the bit is '1':
        i. Increment the counter.
        ii. If the counter reaches 5, insert a '0' bit into the stream and reset the counter to 0.
    b. If the bit is '0':
        i. Reset the counter to 0.
        ii. Transmit the bit.
3. Transmit any remaining bits.
```

**Algorithm 2: Receiver (Bit De-stuffing)**

This algorithm removes the stuffed '0' bits at the receiver.

```
1. Initialize a counter to 0.
2. For each bit in the received stream:
    a. If the bit is '1':
        i. Increment the counter.
    b. If the bit is '0':
        i. If the counter is 5, discard the current '0' bit (stuffed bit) and reset the counter to 0.
        ii. Otherwise, reset the counter to 0 and accept the bit as data.
3. Accept any remaining bits as data.
```

**Explanation:**

These algorithms ensure that the receiver can distinguish between data and control bits. By inserting '0' bits after every five consecutive '1' bits, the sender avoids creating a flag sequence within the data itself. The receiver, knowing this rule, removes the stuffed bits to recover the original data. 

**Note:** These algorithms assume a specific flag sequence (01111110) and stuffing rule. Different protocols might use different flag sequences and stuffing rules. 
