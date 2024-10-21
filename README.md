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
- [](#)
- [](#)
- [](#)

## Intro
1. What is a Network?
- A network consists of two or more computers that are linked in order to share resources.
2. What is Networking?
- Networking, or computer networking, is the process of connecting two or more computing devices.

## Host
1. `Host` are any device sends or reveive traffic for example a Tv, Phone, Laptop etc...

2. There's two types of Hosts :
    - Client : sends request
    - Server : respond to that request

A `Server` is nothing but a computer that can take a request from a device (Client) and sends a response.

## IP Address
Every Host has an identity. and that's the `IP ADDRESS`.

1. So `IP ADDRESS` is the identity of a host.

2. An `IP ADDRESS` is 32 bits.
    - 32 bits is 4 octects because (1 oct == 8 bits).

For example we have this ip address `192.168.1.1`

|  octect  |  octect  |  octect  |  octect  |
| -------- | -------- | -------- | -------- |
|   $\color{red}192.$ | $\color{red}168.$ | $\color{red}1.$ | $\color{yellow}1$ |

$\color{red}Network Portion.$
$\color{yellow}host portion$

3. There are always two IP addresses reserved in a network
    - Network Adress (first IP of the network) (ex. 192.168.1.0)
    - Broadcatst Address (Last IP of the network) (ex 192.168.1.255)

4. So, Usable IP range will be :
    - 192.168.1.1 - 192.168.1.254

## Network
1. A `network` enables two computers to communicate with each other .

![net overview](./assets/images/net_overview.webp "hack the box academy")


## Network Types
| Network Type	                       | Definition                                 |
| -------------------------------------| ------------------------------------------ |
| Wide Area Network (WAN)	           | Internet                                   |
| Local Area Network (LAN)	           | Internal Networks (Ex: Home or Office)     |
| Wireless Local Area Network (WLAN)   | Internal Networks accessible over Wi-Fi    |
| Personal area network                | Like Bluetooth (PTP Network)               |
| Virtual Private Network (VPN)	       | Connects multiple network sites to one LAN |


1. WAN
`Wide Area Network` is commonly referred to as `the Internet`.
A `WAN` is just a large number of `LANs` joined together.

2. LAN and WLAN
`LAN` or `Local Area Network` and `WLAN` or `Wireless Local Area Network` will typically assign IP Addresses designated for local use (RFC 1918, 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16).

3. VPN
`Virtual Private Networks` makes the user feel as if they were plugged into a defferent network.

Types of `VPN` :
1. Site-to-site VPN : both the client and server are devices (routers, firewalls).

2. Remote access VPN : the client computer creates a virtual interface that behaves as if it's on a client's network.

3. SSL VPN : VPN done in a web browser .

## Book Terms

| Network Type	                        | Definition                        |
| ------------------------------------- | --------------------------------- |
| Global Area Network (GAN)	            |   Global network (the Internet)   |
| Metropolitan Area Network (MAN)	    |   Regional network (multiple LANs)|
| Wireless Personal Area Network (WPAN)	|   Personal network (Bluetooth)    |


## Networking Topologies

A network topology is a typical arrangement and physical or logical connection of devices in a network.

- Computers are hosts, such as clients and servers
- They also include network components such as switches, bridges and routers


1. Connections


| Wired connections        | 	Wirelesms connections   |
| ------------------------ | ------------------------- |
| Coaxial cabling	       |         Wi-Fi             |
| Glass fiber cabling	   |         Cellular          |
| Twisted-pair cabling	   |         Satellite         |
| and others	           |         and others        |




## TCP/IP
it's just a list of rules on how data should be sent and received accurately between devices.

1. TCP/IP Protocols (layers) :


| Layer 4 | Applocation | End-user software (web browser)           |
| ------- | ----------- | ----------------------------------------- |
| Layer 3 | Transport   | TCP, UDP, ...                             |
| Layer 2 | Internet    | IP addressing and routing                 |
| Layer 1 | Physical    | Physical transmission of data (eth cables)|


## Subnetting
`Subnetting` is the process of creating a subnetwork (also known as a subnet) within a network.

For example :
- We have a network address `192.168.1.0`
- Subnet `192.168.1.0/24`
- This `CIDR notation` (`/24`) is The Subnet Mask
- Subnet Mask in decimal is :

|  octect  |  octect  |  octect  |  octect  |
| -------- | -------- | -------- | -------- |
|   $\color{red}255.$ | $\color{red}255.$ | $\color{red}255.$ | $\color{yellow}0$ |

- In binary :

|  octect  |  octect  |  octect  |  octect  |
| -------- | -------- | -------- | -------- |
|   $\color{red}11111111.$ | $\color{red}11111111.$ | $\color{red}11111111.$ | $\color{yellow}00000000$ |

- Zeros indicate how many host addresses is available

1. how to convert an octet to bin (easy way)
    - This table method is quick and helps visualize how each bit corresponds to a power of 2

##### Convert 192 to Binary using Powers of 2

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

2. Network class ranges :
    - class A : 1.0.0.0 - 126.255.255.255
    - Class B : 128.0.0.0 - 191.255.0.0
    - Class C : 192.0.0.0 - 223.255.255.0
    - Class D : 224.0.0.0 - 239.255.255.255
    - Class E : 240.0.0.0 - 255.255.255.255


## NAT
NAT (`Network Address Translation)`) : Most home routers use NAT to allow multiple devices to connect to the internet using a single public IP address.