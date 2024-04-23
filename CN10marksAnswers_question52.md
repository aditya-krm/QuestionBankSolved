## Subnet Allocation for ISP Customers:

Here's how we can design the sub-blocks and analyze remaining addresses:

**1. Initial Block:**

*   The ISP has `190.100.0.0/16`, which provides 65,536 addresses.

**2. Group A Requirements:**

*   64 customers each needing 256 addresses.
*   Total addresses needed: 64 customers * 256 addresses/customer = 16,384 addresses.
*   We need a subnet with at least 16,384 addresses. 
*   A `/20` subnet provides 4,096 addresses, so we need 4 of these subnets.
*   Subnet allocation:
    *   `190.100.0.0/20`
    *   `190.100.16.0/20`
    *   `190.100.32.0/20`
    *   `190.100.48.0/20`

**3. Group B Requirements:**

*   128 customers each needing 128 addresses.
*   Total addresses needed: 128 customers * 128 addresses/customer = 16,384 addresses.
*   Similar to Group A, we need 4 subnets of `/20` each.
*   Subnet allocation:
    *   `190.100.64.0/20`
    *   `190.100.80.0/20`
    *   `190.100.96.0/20`
    *   `190.100.112.0/20`

**4. Group C Requirements:**

*   128 customers each needing 64 addresses.
*   Total addresses needed: 128 customers * 64 addresses/customer = 8,192 addresses.
*   A `/21` subnet provides 2,048 addresses, so we need 4 of these subnets.
*   Subnet allocation:
    *   `190.100.128.0/21`
    *   `190.100.136.0/21`
    *   `190.100.144.0/21`
    *   `190.100.152.0/21`

**5. Remaining Addresses:**

*   Total allocated addresses: 16,384 (Group A) + 16,384 (Group B) + 8,192 (Group C) = 40,960 addresses.
*   Remaining addresses: 65,536 (total) - 40,960 (allocated) = 24,576 addresses.

Therefore, after allocating subnets to all three groups, the ISP still has **24,576 addresses available**. 
