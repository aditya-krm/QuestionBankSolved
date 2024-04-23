## Classful Addressing: Waste and Inefficiency

### Class A Waste

Class A addresses utilize the first octet to define the network portion, leaving the remaining three octets for host addresses. This structure results in a massive number of potential hosts per network (2^24 - 2 = 16,777,214). For most organizations, this is far more than necessary, leading to significant address wastage. 

### Class C Limitations

On the other end of the spectrum, Class C addresses only dedicate the first three octets to the network portion, leaving just one octet for hosts (2^8 - 2 = 254). This limited number of hosts is insufficient for medium or large corporations with numerous devices and subnets. 

### Classful Addressing Classes

The classful addressing system categorizes IP addresses into five classes:

* **Class A:** First octet range: 1-126 (0 and 127 are reserved)
* **Class B:** First octet range: 128-191
* **Class C:** First octet range: 192-223
* **Class D:** First octet range: 224-239 (Reserved for Multicasting)
* **Class E:** First octet range: 240-255 (Reserved for Research) 
