## TCP vs UDP: A Tale of Two Protocols

Both TCP and UDP are fundamental communication protocols used for different purposes:

**TCP (Transmission Control Protocol):**

* **Reliable:** Ensures data delivery through error checking and retransmission. 
* **Connection-oriented:** Establishes a connection before data exchange, like a phone call.
* **Ordered:** Delivers data packets in the same order they were sent.
* **Slower:** Due to error checking and connection establishment.
* **Examples:** Web browsing, file transfer, email.

**UDP (User Datagram Protocol):**

* **Unreliable:** Does not guarantee data delivery or order.
* **Connectionless:** No connection needed before sending data, like sending a postcard.
* **Unordered:** Packets may arrive in a different order or get lost.
* **Faster:** No error checking or connection overhead.
* **Examples:** Live streaming, online gaming, DNS lookups.

## Leaky Bucket vs Token Bucket: Taming the Data Flow

Both algorithms control data transmission rates but with different approaches:

**Leaky Bucket:**

* **Analogy:** A bucket with a constant leak rate, regardless of inflow.
* **Function:** Limits the data rate to a fixed constant, smoothing out bursts.
* **Excess data:** Discarded if the bucket overflows.
* **Use case:** Shaping network traffic to ensure consistent flow.

**Token Bucket:**

* **Analogy:** A bucket filled with tokens at a constant rate.
* **Function:** Allows bursts of data within limits, as long as there are enough tokens.
* **Excess tokens:** Can accumulate up to a certain limit, allowing for bursts.
* **Use case:** Rate limiting while allowing for short bursts of activity. 
