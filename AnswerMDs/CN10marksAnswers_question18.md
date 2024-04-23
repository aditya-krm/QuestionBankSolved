## 19. Packet Corruption and Error Checking

**(a) Corrupted Destination Address:**

If a packet's logical destination address at the network layer is corrupted, the packet will not reach its intended destination. Here's what happens:

1. **Routing Failure:** Routers along the path will be unable to determine the next hop for the packet due to the corrupted address.
2. **Packet Discard:**  The packet will eventually be discarded by a router, typically after a certain number of hops or timeouts.
3. **Source Notification (Possible scenarios):**
    * **ICMP Destination Unreachable:**  If a router discards the packet, it may send an ICMP (Internet Control Message Protocol) "Destination Unreachable" message back to the source. This message informs the source that the packet could not be delivered.
    * **Transport Layer Timeout:** If the source computer is expecting an acknowledgment (e.g., TCP) for the sent packet and doesn't receive it within a certain timeframe, it will assume the packet was lost and may attempt retransmission.
    * **Application Layer Timeout:**  The application sending the data may implement its own timeout mechanism and inform the user of a communication failure.

**(b) Necessity of Transport Layer Error Checking:**

Even with error detection at the data link layer between hops, an additional checking mechanism is crucial at the transport layer for the following reasons:

* **End-to-End Error Detection:** Data link layer error detection only ensures data integrity between adjacent hops. It doesn't guarantee error-free delivery across the entire path from source to destination. The transport layer provides end-to-end error checking, ensuring data integrity across the entire network path.
* **Different Error Detection Mechanisms:** Data link layer protocols may use different error detection mechanisms, and some may be less reliable than others. The transport layer provides a consistent and reliable error detection mechanism independent of the underlying network technologies.
* **Handling Undetected Errors:**  While rare, it's possible for errors to go undetected at the data link layer. The transport layer acts as a final safeguard to catch such errors and ensure data integrity.
* **Flow Control and Reliability:** Transport layer protocols like TCP provide additional functionalities like flow control and reliable delivery, which are essential for many applications. These features rely on error detection and retransmission mechanisms to ensure data arrives in the correct order and without corruption. 
