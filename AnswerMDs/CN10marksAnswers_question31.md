## SR-ARQ Frame Transmission Analysis

### a. Frames Transmitted with SR-ARQ

In SR-ARQ, the sender maintains a window of frames that can be sent without waiting for individual acknowledgements. When a frame is lost, only that specific frame needs to be retransmitted, not the entire window.

Given that every 6th frame is lost, let's analyze the transmission:

* **Frames 1-5:** Sent successfully.
* **Frame 6:** Lost.
* **Frames 7-11:** Sent successfully.
* **Frame 12:** Lost.

At this point, Host A receives a negative acknowledgement (NAK) for frame 6. It then retransmits frame 6. Similarly, it later receives a NAK for frame 12 and retransmits it.

**Total frames transmitted:** 10 (original) + 2 (retransmissions) = 12 frames.

**Comparison with Go-Back-N ARQ:**

In Go-Back-N ARQ, if frame 6 is lost, all subsequent frames (7-12) would also need to be retransmitted, even if they were received successfully. This leads to a higher number of transmissions compared to SR-ARQ.

**Total frames transmitted with Go-Back-N ARQ:** 10 (original) + 6 (retransmissions) = 16 frames.

Therefore, SR-ARQ requires fewer transmissions (12 frames) compared to Go-Back-N ARQ (16 frames) in this scenario.

### b. Outstanding Packets in Sender's Window

Based on the given sequence of events:

* **Frames 0-4:** Initially transmitted.
* **Frame 0 times out:** It remains outstanding as it needs retransmission.
* **Frame 5 transmitted:** Now in the window.
* **Frame 1 times out:** It also becomes outstanding.
* **Frame 2 times out:** Another outstanding frame.
* **Frame 6 transmitted:** Added to the window.

Therefore, the outstanding packets in the sender's window are **frames 0, 1, and 2**. 
