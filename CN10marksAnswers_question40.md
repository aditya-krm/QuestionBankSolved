## Problem with the Stop-and-Wait Protocol over UDP for File Transfer

The described protocol, while seemingly straightforward, suffers from a critical flaw when considering potential process crashes: **deadlock due to lost acknowledgments (ACKs).**

Here's the scenario:

1. **Client sends a request:** The client sends a file request to the server.
2. **Server sends data packets:** The server starts sending data packets containing file parts.
3. **Client sends ACKs:** The client sends ACKs for each received data packet.
4. **Crash:** Either the client or the server crashes.

**Problem:**

* **Server crash:** If the server crashes after sending a data packet but before receiving the ACK, it will be unaware of whether the packet reached the client. Upon restart, it won't know whether to re-transmit the packet or move on to the next one.
* **Client crash:** If the client crashes after receiving a data packet but before sending the ACK, the server will be stuck waiting for the ACK indefinitely. 

In both cases, the protocol enters a deadlock state, and the file transfer cannot proceed. The server remains blocked, waiting for an ACK that will never arrive, and the client (if it restarts) doesn't know which packet to expect next.

**Solutions:**

Several solutions can address this deadlock issue:

* **Timeouts:** Implement timeouts on both the client and server sides. If an ACK or data packet is not received within a specific time frame, the sender can assume it was lost and re-transmit.
* **Sequence numbers:** Include sequence numbers in both data packets and ACKs. This allows both sides to identify missing packets and request re-transmissions.
* **Duplicate detection:** Implement mechanisms to detect and discard duplicate packets caused by re-transmissions.
* **Checksums:** Include checksums in data packets to detect data corruption during transmission.

By incorporating these solutions, the protocol can achieve better reliability and handle potential crashes gracefully, ensuring successful file transfer even in the face of network or system failures. 
