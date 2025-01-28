# NETPRACTICE
- [Intro](#intro)
- [Host](#host)
- [IP Address](#ip-address)
- [Network](#network)
- [Network Types](#network-types)
- [Book Terms](#book-terms)
- [Networking Topologies](#networking-topologies)
- [TCP/IP](#tcpip)
- [Subnetting](#subnetting)
- [NAT](#nat)
- [OSI Model](#osi-model)
- [DNS](#dns)
- [DHCP](#dhcp)

## Intro
1. **What is a Network?**
   - A network consists of two or more computers that are linked in order to share resources (such as files, printers, and internet connections).

2. **What is Networking?**
   - Networking, or computer networking, is the process of connecting two or more computing devices to share data and resources.

## Host
1. **Host**:
   - A host is any device that sends or receives traffic. Examples include TVs, phones, laptops, etc.

2. **Types of Hosts**:
   - **Client**: Sends requests.
   - **Server**: Responds to requests.

   A **Server** is essentially a computer that can take a request from a device (Client) and send a response.

## IP Address
Every host has an identity, which is its **IP Address**.

1. **IP Address**:
   - An IP Address is the identity of a host.

2. **Structure of an IP Address**:
   - An IP Address is 32 bits long, divided into 4 octets (1 octet = 8 bits).

   For example, consider the IP address `192.168.1.1`:

   |  Octet  |  Octet  |  Octet  |  Octet  |
   | -------- | -------- | -------- | -------- |
   |   $\color{red}192.$ | $\color{red}168.$ | $\color{red}1.$ | $\color{yellow}1$ |

   - $\color{red}Network Portion$
   - $\color{yellow}Host Portion$

3. **Reserved IP Addresses**:
   - **Network Address**: The first IP of the network (e.g., `192.168.1.0`).
   - **Broadcast Address**: The last IP of the network (e.g., `192.168.1.255`).

4. **Usable IP Range**:
   - `192.168.1.1` - `192.168.1.254`

## Network
1. **Network**:
   - A network enables two or more computers to communicate with each other.

   ![Network Overview](./assets/images/net_overview.webp "Hack The Box Academy")

## Network Types
| Network Type	                       | Definition                                 |
| -------------------------------------| ------------------------------------------ |
| Wide Area Network (WAN)	           | Internet                                   |
| Local Area Network (LAN)	           | Internal Networks (Ex: Home or Office)     |
| Wireless Local Area Network (WLAN)   | Internal Networks accessible over Wi-Fi    |
| Personal Area Network (PAN)          | Like Bluetooth (PTP Network)               |
| Virtual Private Network (VPN)	       | Connects multiple network sites to one LAN |

1. **WAN**:
   - **Wide Area Network** is commonly referred to as **the Internet**.
   - A WAN is a large number of LANs joined together.

2. **LAN and WLAN**:
   - **LAN** or **Local Area Network** and **WLAN** or **Wireless Local Area Network** typically assign IP Addresses designated for local use (RFC 1918, 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16).

3. **VPN**:
   - **Virtual Private Networks** make the user feel as if they were plugged into a different network.

   **Types of VPN**:
   1. **Site-to-site VPN**: Both the client and server are devices (routers, firewalls).
   2. **Remote access VPN**: The client computer creates a virtual interface that behaves as if it's on a client's network.
   3. **SSL VPN**: VPN done in a web browser.

## Book Terms
| Network Type	                        | Definition                        |
| ------------------------------------- | --------------------------------- |
| Global Area Network (GAN)	            |   Global network (the Internet)   |
| Metropolitan Area Network (MAN)	    |   Regional network (multiple LANs)|
| Wireless Personal Area Network (WPAN)	|   Personal network (Bluetooth)    |

## Networking Topologies
A network topology is a typical arrangement and physical or logical connection of devices in a network.

- **Computers** are hosts, such as clients and servers.
- **Network components** include switches, bridges, and routers.

1. **Connections**:

| Wired Connections        | 	Wireless Connections   |
| ------------------------ | ------------------------- |
| Coaxial cabling	       |         Wi-Fi             |
| Glass fiber cabling	   |         Cellular          |
| Twisted-pair cabling	   |         Satellite         |
| and others	           |         and others        |

## TCP/IP
TCP/IP is a set of rules on how data should be sent and received accurately between devices.

1. **TCP/IP Protocols (Layers)**:

| Layer 4 | Application | End-user software (web browser)           |
| ------- | ----------- | ----------------------------------------- |
| Layer 3 | Transport   | TCP, UDP, ...                             |
| Layer 2 | Internet    | IP addressing and routing                 |
| Layer 1 | Physical    | Physical transmission of data (eth cables)|

## Subnetting
**Subnetting** is the process of creating a subnetwork (also known as a subnet) within a network.

For example:
- We have a network address `192.168.1.0`
- Subnet `192.168.1.0/24`
- This **CIDR notation** (`/24`) is the Subnet Mask.
- Subnet Mask in decimal is:

|  Octet  |  Octet  |  Octet  |  Octet  |
| -------- | -------- | -------- | -------- |
|   $\color{red}255.$ | $\color{red}255.$ | $\color{red}255.$ | $\color{yellow}0$ |

- In binary:

|  Octet  |  Octet  |  Octet  |  Octet  |
| -------- | -------- | -------- | -------- |
|   $\color{red}11111111.$ | $\color{red}11111111.$ | $\color{red}11111111.$ | $\color{yellow}00000000$ |

- Zeros indicate how many host addresses are available.

1. **How to Convert an Octet to Binary (Easy Way)**:
   - This table method is quick and helps visualize how each bit corresponds to a power of 2.

   **Convert 192 to Binary using Powers of 2**:

   | Power of 2 | Value  | Binary Place |
   |------------|--------|--------------|
   | 2^7        | 128    | 1            |
   | 2^6        | 64     | 1            |
   | 2^5        | 32     | 0            |
   | 2^4        | 16     | 0            |
   | 2^3        | 8      | 0            |
   | 2^2        | 4      | 0            |
   | 2^1        | 2      | 0            |
   | 2^0        | 1      | 0            |

   **192 in binary** = `11000000`

2. **Network Class Ranges**:
   - **Class A**: 1.0.0.0 - 126.255.255.255
   - **Class B**: 128.0.0.0 - 191.255.0.0
   - **Class C**: 192.0.0.0 - 223.255.255.0
   - **Class D**: 224.0.0.0 - 239.255.255.255
   - **Class E**: 240.0.0.0 - 255.255.255.255

## NAT
**NAT (Network Address Translation)**:
- Most home routers use NAT to allow multiple devices to connect to the internet using a single public IP address.
- NAT translates private IP addresses within a local network to a public IP address for communication over the internet.

## OSI Model
The **OSI (Open Systems Interconnection)** model is a conceptual framework used to understand and implement standard protocols in network communications.

1. **OSI Model Layers**:

| Layer 7 | Application | Provides network services directly to end-user applications (e.g., HTTP, FTP) |
| ------- | ----------- | ------------------------------------------------------------------------------ |
| Layer 6 | Presentation | Translates data between the application layer and the network format (e.g., encryption) |
| Layer 5 | Session     | Manages sessions between applications (e.g., establishing, managing, and terminating connections) |
| Layer 4 | Transport   | Ensures data transfer reliability (e.g., TCP, UDP)                             |
| Layer 3 | Network     | Handles routing and forwarding of data packets (e.g., IP)                      |
| Layer 2 | Data Link   | Provides node-to-node data transfer (e.g., Ethernet, MAC addresses)            |
| Layer 1 | Physical    | Transmits raw bit streams over a physical medium (e.g., cables, switches)      |

## DNS
**DNS (Domain Name System)**:
- DNS translates human-readable domain names (e.g., www.example.com) into IP addresses that computers use to identify each other on the network.
- DNS operates on the Application Layer (Layer 7) of the OSI model.

## DHCP
**DHCP (Dynamic Host Configuration Protocol)**:
- DHCP automatically assigns IP addresses and other network configuration parameters (e.g., subnet mask, default gateway) to devices on a network.
- DHCP operates on the Application Layer (Layer 7) of the OSI model.
