# Basics of System Design&#x20;

* [Load Balancing](load-balancing.md)
* [Caching](caching.md)
* [Data Partitioning](data-partitioning.md)
* [Indexes](indexes.md)
* [Proxies](proxies.md)
* [Redundancy and Replication](redundancy-and-replication.md)
* [SQL vs. NoSQL](sql-vs.-nosql.md)
* CAP Theorem

## System Design Basics

Whenever we are designing a large system, we need to consider a few things:

1. What are the different architectural pieces that can be used?
2. How do these pieces work with each other?
3. How can we best utilize these pieces: what are the right tradeoffs?

## Key Characteristics of Distributed Systems

* [Scalability](./#scalability)
* [Reliability](./#reliability)
* [Availability](./#availability)
* [Efficiency](./#efficiency)
* [Serviceability or Manageability](./#serviceability-or-manageability)

### Scalability <a href="#scalability" id="scalability"></a>

&#x20; Scalability is the capability of a system, process, or a network to grow and manage increased demand. Any distributed system that can continuously evolve in order to support the growing amount of work is considered to be scalable.

&#x20; **Horizontal vs. Vertical Scaling:** Horizontal scaling means that you scale by adding more servers into your pool of resources whereas Vertical scaling means that you scale by adding more power (CPU, RAM, Storage, etc.) to an existing server.

&#x20; With horizontal-scaling it is often easier to scale dynamically by adding more machines into the existing pool; Vertical-scaling is usually limited to the capacity of a single server and scaling beyond that capacity often involves downtime and comes with an upper limit.

&#x20; Good examples of horizontal scaling are [Cassandra](https://en.wikipedia.org/wiki/Apache\_Cassandra) and [MongoDB](https://en.wikipedia.org/wiki/MongoDB) as they both provide an easy way to scale horizontally by adding more machines to meet growing needs. Similarly, a good example of vertical scaling is MySQL as it allows for an easy way to scale vertically by switching from smaller to bigger machines. However, this process often involves downtime.

![](<../../.gitbook/assets/image (24) (1) (1) (1) (1).png>)

### Reliability <a href="#reliability" id="reliability"></a>

&#x20; By definition, reliability is the probability a system will fail in a given period. In simple terms, a distributed system is considered reliable if it keeps delivering its services even when one or several of its software or hardware components fail. Reliability represents one of the main characteristics of any distributed system, since in such systems any failing machine can always be replaced by another healthy one, ensuring the completion of the requested task.

&#x20; Take the example of a large electronic commerce store (like [Amazon](https://en.wikipedia.org/wiki/Amazon\_\(company\))), where one of the primary requirement is that any user transaction should never be canceled due to a failure of the machine that is running that transaction. For instance, if a user has added an item to their shopping cart, the system is expected not to lose it. A reliable distributed system achieves this through redundancy of both the software components and data. If the server carrying the user’s shopping cart fails, another server that has the exact replica of the shopping cart should replace it.

&#x20; Obviously, redundancy has a cost and a reliable system has to pay that to achieve such resilience for services by eliminating every single point of failure.

### Availability <a href="#availability" id="availability"></a>

&#x20; By definition, availability is the time a system remains operational to perform its required function in a specific period. It is a simple measure of the percentage of time that a system, service, or a machine remains operational under normal conditions. An aircraft that can be flown for many hours a month without much downtime can be said to have a high availability. Availability takes into account maintainability, repair time, spares availability, and other logistics considerations. If an aircraft is down for maintenance, it is considered not available during that time.

&#x20; Reliability is availability over time considering the full range of possible real-world conditions that can occur. An aircraft that can make it through any possible weather safely is more reliable than one that has vulnerabilities to possible conditions.

**Reliability Vs. Availability**\
&#x20; If a system is reliable, it is available. However, if it is available, it is not necessarily reliable. In other words, high reliability contributes to high availability, but it is possible to achieve a high availability even with an unreliable product by minimizing repair time and ensuring that spares are always available when they are needed. Let’s take the example of an online retail store that has 99.99% availability for the first two years after its launch. However, the system was launched without any information security testing. The customers are happy with the system, but they don’t realize that it isn’t very reliable as it is vulnerable to likely risks. In the third year, the system experiences a series of information security incidents that suddenly result in extremely low availability for extended periods of time. This results in reputational and financial damage to the customers.

### Efficiency <a href="#efficiency" id="efficiency"></a>

&#x20; To understand how to measure the efficiency of a distributed system, let’s assume we have an operation that runs in a distributed manner and delivers a set of items as result. Two standard measures of its efficiency are the response time (or latency) that denotes the delay to obtain the first item and the throughput (or bandwidth) which denotes the number of items delivered in a given time unit (e.g., a second). The two measures correspond to the following unit costs:

* Number of messages globally sent by the nodes of the system regardless of the message size.
* Size of messages representing the volume of data exchanges.

&#x20; The complexity of operations supported by distributed data structures (e.g., searching for a specific key in a distributed index) can be characterized as a function of one of these cost units. Generally speaking, the analysis of a distributed structure in terms of ‘number of messages’ is over-simplistic. It ignores the impact of many aspects, including the network topology, the network load, and its variation, the possible heterogeneity of the software and hardware components involved in data processing and routing, etc. However, it is quite difficult to develop a precise cost model that would accurately take into account all these performance factors; therefore, we have to live with rough but robust estimates of the system behavior.

### Serviceability or Manageability <a href="#serviceability-or-manageability" id="serviceability-or-manageability"></a>

&#x20; Another important consideration while designing a distributed system is how easy it is to operate and maintain. Serviceability or manageability is the simplicity and speed with which a system can be repaired or maintained; if the time to fix a failed system increases, then availability will decrease. Things to consider for manageability are the ease of diagnosing and understanding problems when they occur, ease of making updates or modifications, and how simple the system is to operate (i.e., does it routinely operate without failure or exceptions?).

&#x20; Early detection of faults can decrease or avoid system downtime. For example, some enterprise systems can automatically call a service center (without human intervention) when the system experiences a system fault.
