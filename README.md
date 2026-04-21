*This project has been created as part of the 42 curriculum by rmedeiro.*

# NetPractice

## Description

NetPractice is a networking project from the 42 curriculum designed to develop a solid and practical understanding of TCP/IP communication, routing mechanisms, and network structure.

Throughout this project, we explore how computer networks operate, how IP addressing is configured, and how to connect devices and allow them to communicate with each other to exchange data correctly.

The project is composed of multiple network configuration exercises with increasing difficulty, where the goal is to correctly configure IP addresses, subnet masks, and routing configurations so that hosts can communicate both within the same network and across different networks.

By solving these exercises, we develop a clear understanding of packet flow, router decision-making, and how subnetting enables efficient network organization. Each level presents a incomplete network topology that must be fixed by assigning correct addressing and routing logic to restore connectivity.

---

## Instructions

### How to launch it

NetPractice uses a browser-based interface supplied by 42.

To start the interface, execute:

```bash

./run.sh

```

This command will automatically open the NetPractice interface in your default web browser.

---

### How the interface works

Each level displays a network tipology composed of multiple elements, including:


* Hosts

* Routers

* Switches

* Internet nodes

* Each network interface can be configured with:

  * IP address

  * Subnet mask

  * Default gateway

  * Routing table entries

The goal is to correctly configure these parameters so that communication between the specified nodes is successfully established.

Once the configuration is complete, the result can be validated using the **Check solution** button, which verifies connectivity and correctness of the network setup.

---

### Exporting configurations

After successfully completing a level:

1. Click on **Get my config** button

2. Download the generated exported configuration file

3. Place the file at the **root of your Git repository**, as required by the subject

---

### Submission requirements

The final repository must include:

* Exactly **10 exported configuration files**

* One file corresponding to each level

* All files must be placed at the repository root

```

NetPractice/

├── README.md

├── level1.json

├── level2.json

├── level3.json

├── level4.json

├── level5.json

├── level6.json

├── level7.json

├── level8.json

├── level9.json

└── level10.json

```

---

## Concepts Learned

This project provides hands-on experience with fundamental networking concepts and how they interact in real world scenarios.

### TCP/IP addressing

IP Address stands for internet protocol, it's a list of guidelines that a device must follow if it wants to communicate with other devices. There are two models OSI (Open Systems Interconnection) and TCP (Transmission Control Protocol) but we mostly use TCP.

IPv4 addressing is used to uniquely identify devices within a network. An IP address is a 32-bit value represented in dotted decimal format and is divided into two parts:

- Network portion: identifies the network  
- Host portion: identifies the device within that network  

The separation between these two parts is defined by the subnet mask.

### Subnet Masks and Subnetting

A subnet mask determines which bits of an IP address belong to the network and which belong to the host.

Each subnet has reserved addresses:

- First address: network address  
- Last address: broadcast address  

### Default Gateway

A default gateway is the router used by a host to communicate with devices outside its local network.

When a destination IP is not part of the local subnet, packets are forwarded to the default gateway, which then routes them to the appropriate network.

---

### Routing

Routing is the process of sending data from one network to another.

Routers use routing tables to decide where each packet should go.

They choose the best path using **longest prefix matching**, meaning the most specific route is preferred.

---

### Network Hierarchy and Summarization

Networks are often organized in layers to make them easier to manage and scale.

Route summarization allows multiple networks to be grouped into a single route, which helps to:

- Reduce the size of routing tables  
- Improve performance  

This is especially useful in large networks.

---

### Router Behavior

Routers work at **Layer 3 (Network layer)** and connect different networks.

They:

- Check the destination IP address  
- Choose the correct path  
- Send the packet to the next network  

They use routing tables to make these decisions.

---

### Switch Behavior

Switches work at **Layer 2 (Data Link layer)** and connect devices within the same network.

They send data using **MAC addresses**, deciding where to forward it based on a MAC address table.

Switches do not route traffic and cannot connect different networks.

### OSI and TCP/IP Models

Networking is structured in layers to separate responsibilities.

#### OSI Model

The OSI model is a reference model that divides networking into layers:

* Layer 1 - Physical (hardware, cables, signals)

* Layer 2 - Data Link (switching, MAC addresses)

* Layer 3 - Network (IP addressing and routing)

* Layer 4 - Transport (TCP/UDP communication)

#### TCP/IP Model

The TCP/IP model is the one most commonly used in real networks. It is divided into 4 layers:

* **Application:** defines/selects which protocol it needs to use (HTTP, HTTPS, FTP, etc)

* **Transport:** controls/decides how the data is sent.

  - TCP (Transmission Control Protocol): reliable, connection-oriented, but slower. Assures that the data was received before sending more.
  - UDP (User Datagram Protocol): faster, connectionless. Sends data without doing any checks. Needs a port to know where to send the info and what permissions it has (like SSH).

* **Network:** responsible for identification of source and destination of the data we are sending and the path it should take.

* **Link (Access):** handles physical transmission and uses MAC (Medium Access Control) addresses to send data between devices.


### How communication works

When a device wants to communicate with another first checks if the destination is in the same network.

This is done using:

- IP address -> identifies the device  
- Subnet mask -> defines the network boundary  

If both devices are in:

- **Same network ->** communication is direct  
- **Different networks ->** data is sent to a router (default gateway)  

---

### Key elements

- **IP address:** set of 4 numbers (0-255) assigned to each device  
- **Subnet mask:** defines which part of the IP is network/host  
- **Network address:** first IP of the subnet (reserved)  
- **Broadcast address:** last IP of the subnet (reserved)  

---

## Resources

### Educational References

* Subnetting tutorials on Youtube and CIDR reference guides

	https://en.wikipedia.org/wiki/IP_routing

	https://www.youtube.com/playlist?list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF

	https://networklessons.com/ip-routing/ip-routing-explained

	https://www.geeksforgeeks.org/computer-networks/differences-between-tcp-and-udp/

	https://www.geeksforgeeks.org/computer-networks/tcp-ip-model/


* Chatgpt (see AI Usage Disclosure)

---

### AI Usage Disclosure

AI tools were used to:

* Clarify router behavior and routing table matching

* Help develop a structured methodology for network configuration

AI was not used to directly generate or solve the NetPractice configurations. All network configurations were completed manually to ensure full understanding of the underlying networking concepts.

---
