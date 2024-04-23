## Distance Vector vs. Link State Routing: Key Differences

The main difference between distance vector and link state routing lies in how they determine the best path to a destination:

**Distance Vector Routing:**

* **Focus:** Each router only knows about its directly connected neighbors and their distances (costs) to various networks.
* **Information Sharing:** Routers periodically share their routing tables with their immediate neighbors. 
* **Path Determination:**  Each router calculates the best path based on the information received from its neighbors, considering the distance (cost) as the primary metric. 
* **Examples:** Routing Information Protocol (RIP), Interior Gateway Routing Protocol (IGRP)

**Link State Routing:**

* **Focus:** Each router builds a complete map of the network topology by gathering information about all links and routers in the network.
* **Information Sharing:** Routers flood link-state advertisements (LSAs) throughout the entire network, informing all other routers about the state of their directly connected links.
* **Path Determination:** Each router independently constructs a shortest path tree using Dijkstra's algorithm or a similar method, considering various metrics like bandwidth, delay, and cost.
* **Examples:** Open Shortest Path First (OSPF), Intermediate System-to-Intermediate System (IS-IS) 

Here's a table summarizing the key differences:

| Feature                 | Distance Vector Routing | Link State Routing |
| ----------------------- | ----------------------- | ------------------ |
| **Knowledge Scope**      | Local (neighbors)       | Global (entire network) |
| **Information Sharing** | Periodic updates with neighbors | Flooding of LSAs to all routers |
| **Path Calculation**    | Based on neighbor information | Independent calculation using complete network map |
| **Convergence Speed**  | Slower                 | Faster              |
| **Scalability**         | Limited                | More scalable      |
| **Complexity**          | Simpler                | More complex       | 
