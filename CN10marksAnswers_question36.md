## Bidirectional Algorithm for Simplest and Stop & Wait Protocol with Piggybacking

This algorithm outlines the sending and receiving processes for both parties (A and B) in a bidirectional communication using the Simplest Protocol and Stop & Wait ARQ with piggybacking. Both parties will follow the same logic.

**Variables:**

*   **SND_BUF**: Buffer to store data to be sent.
*   **RCV_BUF**: Buffer to store received data.
*   **SEND_FLAG**: Flag indicating if there is data to send (1) or not (0).
*   **ACK_FLAG**: Flag indicating if an acknowledgment needs to be sent (1) or not (0).
*   **SEQ**: Sequence number of the current data packet (0 or 1).
*   **ACK**: Acknowledgment number expected for the next packet (0 or 1).

**Algorithm:**

1.  **Initialization:**
    *   Set `SEND_FLAG` and `ACK_FLAG` to 0.
    *   Set `SEQ` and `ACK` to 0.

2.  **Sending Process:**
    *   **If `SND_BUF` has data and `SEND_FLAG` is 0:**
        *   Create a packet with the data, `SEQ`, and `ACK`.
        *   Set `SEND_FLAG` to 1.
        *   Send the packet.
        *   Start a timer.
    *   **If timer expires:**
        *   Resend the last packet.
        *   Restart the timer.
    *   **If an ACK packet is received:**
        *   If the received `ACK` matches the expected `SEQ`, the packet was successfully received.
        *   Set `SEND_FLAG` to 0.
        *   Toggle `SEQ` (0 becomes 1, 1 becomes 0).
        *   Stop the timer.

3.  **Receiving Process:**
    *   **If a data packet is received:**
        *   If the received `SEQ` matches the expected `ACK`:
            *   Extract the data from the packet and store it in `RCV_BUF`.
            *   Set `ACK_FLAG` to 1.
            *   Toggle `ACK` (0 becomes 1, 1 becomes 0).
        *   Send an ACK packet with the current `ACK` value.
    *   **If `SND_BUF` has data and `ACK_FLAG` is 1 (piggybacking):**
        *   Create a packet with the data, `SEQ`, and `ACK`.
        *   Set `SEND_FLAG` and `ACK_FLAG` to 1.
        *   Send the packet.
        *   Start a timer.
    *   **If `ACK_FLAG` is 1 and there is no data to send:**
        *   Send an ACK packet with the current `ACK` value.
        *   Set `ACK_FLAG` to 0.

**Notes:**

*   This algorithm uses piggybacking, meaning acknowledgments are included in data packets whenever possible to reduce the number of packets sent.
*   The timer is used to handle packet loss. If an acknowledgment is not received within a certain time, the packet is assumed lost and re-sent.
*   The `SEQ` and `ACK` numbers are toggled between 0 and 1 to ensure that duplicate packets are not processed. 
*   Both parties must use the same logic and timing parameters for the algorithm to function correctly. 
