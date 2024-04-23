## CRC Calculation and Error Detection

### a. Transmitting the Message with CRC

To transmit the message with CRC error detection, we need to append the CRC checksum to the original message. Here's how we find the checksum using polynomial long division:

**1. Append 0s:**

- Add 3 zeros (degree of C(x)) to the message P(x) to create P'(x):
    - P'(x) = 11001001000

**2. Divide P'(x) by C(x):**

- Perform polynomial long division of P'(x) by C(x) = x^3 + 1:
    - 11001001000 / 1001 = 11000110 (quotient) with a remainder of 100 (CRC checksum)

**3. Append Checksum:**

- Append the remainder (100) to the original message:
    - Transmitted message T(x) = 11001001100

Therefore, the transmitted message is 11001001100.

### b. Error Detection with CRC

**Scenario:** The leftmost bit is inverted due to noise, resulting in the received message R(x) = 01001001100.

**Receiver's CRC Calculation:**

1. Divide R(x) by C(x):
    - 01001001100 / 1001 = 01000110 with a remainder of 011 (not equal to 0)

**Error Detection:**

Since the remainder is not zero, the receiver knows an error has occurred during transmission.

### Undetectable Errors

**Example:**

Consider an error pattern that flips the following bits in the transmitted message:

- Original: 11001001100
- Error pattern: 00100000000 (XORed with the original)
- Result: 11101001100

This specific error pattern results in a new message that is still divisible by C(x) and therefore will not be detected by the CRC check.

**General Pattern:**

Undetectable errors occur when the error pattern itself is a multiple of the CRC polynomial C(x). This is because the division by C(x) will result in a remainder of 0, indicating no error even though the message has been corrupted. 
