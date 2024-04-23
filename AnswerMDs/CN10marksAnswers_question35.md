## Socket Pairs in SNMP and TFTP Communication

### a. SNMP Communication

*   **Client Socket:** (122.45.12.7, random port number) 
*   **Server Socket:** (200.112.45.90, 161)

**Explanation:**

*   The SNMP client initiates the communication by sending a request from a randomly chosen port on its IP address (122.45.12.7) to the well-known SNMP port 161 on the server's IP address (200.112.45.90).

### b. TFTP Communication

*   **Server Socket:** (130.45.12.7, 69)
*   **Client Socket:** (14.90.90.33, random port number) 

**Explanation:**

*   The TFTP server, unlike many client-server models, initiates the data transfer after the client requests a file.  The server sends the data from its well-known TFTP port 69 on its IP address (130.45.12.7) to a randomly chosen port on the client's IP address (14.90.90.33). 
