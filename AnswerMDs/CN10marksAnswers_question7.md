## Short Notes on Networking Concepts:

### Firewall

* A firewall acts as a barrier between a trusted internal network and untrusted external networks, like the internet. 
* It examines incoming and outgoing network traffic and blocks any traffic that does not match its configured security rules.
* Firewalls can be implemented in hardware or software, or a combination of both.
* They are crucial for protecting against unauthorized access, malware, and other cyber threats.

### POP3 vs. IMAP

Both POP3 and IMAP are protocols used to access email from a mail server. However, they differ in how they manage emails:

* **POP3 (Post Office Protocol 3):**
    * Downloads emails from the server to the client device.
    * Emails are typically deleted from the server after download.
    * Better for users who primarily access email from one device and want to save storage space on the server.
* **IMAP (Internet Message Access Protocol):**
    * Synchronizes emails across multiple devices.
    * Emails are stored on the server and can be accessed from any device.
    * Offers more features, such as creating folders and flagging messages.
    * Better for users who access email from multiple devices and want to keep their inbox consistent.

### ARP vs. RARP

Both ARP and RARP are protocols used to resolve addresses in a network, but they work in opposite directions:

* **ARP (Address Resolution Protocol):**
    * Resolves an IP address (logical address) to a MAC address (physical address).
    * Used when a device wants to communicate with another device on the same local network.
* **RARP (Reverse Address Resolution Protocol):**
    * Resolves a MAC address to an IP address.
    * Used by devices without a configured IP address to obtain one from a RARP server. 
    * **Largely obsolete** and replaced by DHCP (Dynamic Host Configuration Protocol). 
