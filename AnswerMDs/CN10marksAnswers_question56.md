## Subnet Allocation for ISP Customers:

Here's how we can design the sub-blocks for the ISP's customers:

**a) Medium-sized businesses:**

*   Number of businesses: 200
*   Addresses per business: 128 (2^7)
*   Total addresses needed: 200 * 128 = 25600

To accommodate 128 addresses, we need a subnet mask of /25 (as 2^7 = 128 and 32 - 7 = 25).  Therefore, each medium business will get a /25 block.

**b) Small businesses:**

*   Number of businesses: 400
*   Addresses per business: 16 (2^4)
*   Total addresses needed: 400 * 16 = 6400

To accommodate 16 addresses, we need a subnet mask of /28 (as 2^4 = 16 and 32 - 4 = 28).  Therefore, each small business will get a /28 block.

**c) Households:**

*   Number of households: 2000
*   Addresses per household: 4 (2^2)
*   Total addresses needed: 2000 * 4 = 8000 

To accommodate 4 addresses, we need a subnet mask of /30 (as 2^2 = 4 and 32 - 2 = 30).  Therefore, each household will get a /30 block.

## Subnet Summary:

*   **Medium businesses:** 200 subnets with /25 mask
*   **Small businesses:** 400 subnets with /28 mask
*   **Households:** 2000 subnets with /30 mask 

## Remaining Addresses:

*   Total addresses in /16 block: 2^16 = 65536
*   Addresses allocated: 25600 (medium) + 6400 (small) + 8000 (households) = 40000
*   **Remaining addresses:** 65536 - 40000 = 25536 
