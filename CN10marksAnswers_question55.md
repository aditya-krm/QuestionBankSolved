## Subnet Allocation for ISP Customers:

Here's how we can design the sub-blocks for each customer group:

**a. Medium-Sized Businesses (200 businesses, 128 addresses each):**

*   **Addresses needed:** 200 businesses * 128 addresses/business = 25,600 addresses 
*   **Subnet mask:** We need at least 25,600 addresses, which is more than 16,384 (2^14) but less than 32,768 (2^15). So, we need a /15 subnet mask.
*   **Subnet allocation:** 150.80.0.0/15 
*   **Usable addresses:** This block provides 32,768 addresses, leaving 32,768 - 25,600 = 7,168 addresses unused within this block.

**b. Small Businesses (400 businesses, 16 addresses each):**

*   **Addresses needed:** 400 businesses * 16 addresses/business = 6,400 addresses
*   **Subnet mask:** We need at least 6,400 addresses, which is more than 4,096 (2^12) but less than 8,192 (2^13). So, we need a /13 subnet mask.
*   **Subnet allocation:** We can allocate two /13 subnets:
    *   150.80.32.0/13
    *   150.80.48.0/13
*   **Usable addresses:** Each /13 block provides 8,192 addresses, so two blocks provide 16,384 addresses. This leaves 16,384 - 6,400 = 9,984 addresses unused within these blocks.

**c. Households (2000 households, 4 addresses each):**

*   **Addresses needed:** 2000 households * 4 addresses/household = 8,000 addresses
*   **Subnet mask:** We need at least 8,000 addresses, which is more than 4,096 (2^12) but less than 8,192 (2^13). So, we need a /13 subnet mask.
*   **Subnet allocation:** We can allocate two /13 subnets:
    *   150.80.64.0/13 
    *   150.80.80.0/13
*   **Usable addresses:** Similar to the small businesses, these two /13 blocks provide 16,384 addresses, leaving 16,384 - 8,000 = 8,384 addresses unused within these blocks. 

## Summary of Allocations:

| Customer Group       | Number of Customers | Addresses per Customer | Subnet Mask | Subnet Allocation(s)     |
| -------------------- | ------------------ | ---------------------- | ----------- | ------------------------ |
| Medium Businesses    | 200                 | 128                   | /15         | 150.80.0.0/15            |
| Small Businesses     | 400                 | 16                    | /13         | 150.80.32.0/13, 150.80.48.0/13 |
| Households           | 2000                | 4                     | /13         | 150.80.64.0/13, 150.80.80.0/13 |

## Remaining Addresses:

*   The initial block (150.80.0.0/16) contains 65,536 addresses.
*   We have allocated a total of 25,600 (medium) + 6,400 (small) + 8,000 (households) = 40,000 addresses.
*   Therefore, 65,536 - 40,000 = 25,536 addresses are still available. 
