## CRC Relationships: Data, Code, Divisor, and Remainder

Here's a breakdown of the relationships between the entities you mentioned in the context of Cyclic Redundancy Checks (CRC):

**a. Data-word size and Code-word size:**

*   **Direct Relationship:** The size of the code-word is always larger than the data-word. 
*   **Difference:** The difference in size between the code-word and data-word is equal to the size of the CRC bits (checksum) appended to the data-word. 
*   **Example:** If you have a 16-bit data-word and use a CRC that generates an 8-bit checksum, the resulting code-word will be 24 bits long.

**b. Divisor size and Remainder size:**

*   **Fixed Relationship:** The size of the remainder is always one bit less than the size of the divisor.
*   **Reason:** This is due to the nature of the polynomial division used in CRC calculations. The remainder represents the "leftover" bits after dividing the data-word (augmented with 0s) by the divisor polynomial.
*   **Example:** If you use a 17-bit divisor, the remainder will always be 16 bits long.

**c. Degree of polynomial generator and size of the divisor:**

*   **Direct Relationship:** The degree of the generator polynomial is equal to the size of the divisor minus 1.
*   **Reason:** The degree signifies the highest power of x in the polynomial. In CRC, the divisor is represented as a polynomial with a leading coefficient of 1. 
*   **Example:** A divisor of size 17 bits corresponds to a generator polynomial of degree 16.

**d. Degree of polynomial generator and size of the remainder:**

*   **Fixed Relationship:** The degree of the generator polynomial is always one more than the size of the remainder.
*   **Reason:** This relationship follows from points b and c above. Since the remainder size is one less than the divisor size, and the divisor size is one more than the generator polynomial degree, the degree is consequently one more than the remainder size.
*   **Example:** If the generator polynomial has a degree of 16, the remainder will be 15 bits long. 
