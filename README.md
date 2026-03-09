# NetPractice

*This project has been created as part of the 42 curriculum by eldiaz-c*

## Description

NetPractice is a practical networking project focused on understanding the fundamentals of TCP/IP addressing and basic network configuration.

The objective of this project is to correctly configure small-scale networks by assigning valid IP addresses, subnet masks, and default gateways in order to make the network functional or to restore communication between devices.

The project consists of 10 levels of increasing difficulty. Each level presents a non-functioning network diagram that must be fixed by adjusting the available configuration fields. This requires analyzing addressing, identifying subnet boundaries, and ensuring proper routing between networks. 

The project is solved through logical reasoning and manual subnet calculations without relying on automated networking tools.

Through this project, I developed a deeper understanding of how devices communicate within a network and how routing works between different subnets (logical reasoning, subnet calculation, routing).

---

## Instructions

1. Download the project files from the NetPractice page.
2. Extract the files into a local directory.
3. Open the `index.html` file in a web browser.

    If the script does not work, you can manually start the server:

    `python3 -m http.server 49242`

    Then open in your browser:
    `http://localhost:49242`

4. Enter your login to generate your personal configuration.
5. Solve each of the 10 levels by correcting the network configuration.
6. After completing a level, click on **Get my config** to export the configuration file.
7. Place the 10 exported configuration files (one per level) at the root of your Git repository before submission.

During evaluation, three random levels must be solved within a limited time. External tools are not allowed, except for simple calculation tools such as `bc`.

---

## Networking Concepts

This project covers the following networking concepts:

- TCP/IP addressing
- IPv4 structure (32-bit addressing)
- Network and host parts of an IP address
- Subnet masks and CIDR notation
- Broadcast address
- Default gateway
- Router behavior and packet forwarding
- Switch role in local network communication
- Communication between different subnets (inter-subnet routing)

---

## Glossary

### IP Address

A unique numerical identifier assigned to each device on a network. In IPv4 it consists of 32 bits divided into four octets.

### Subnet Mask

A value used to divide an IP address into network and host portions, determining which part identifies the network and which part identifies the device.

### CIDR (Classless Inter-Domain Routing)

A notation used to represent subnet masks compactly using a suffix such as /24 or /26, indicating how many bits belong to the network.

### Broadcast Address

The last address in a subnet, used to send a packet to all devices in the subnet simultaneously.

Example:

`192.168.1.63`

### Network Address

The first address of a subnet, which identifies the network itself. It cannot be assigned to a device.

Example:

`192.168.1.0`

### Gateway (Default Gateway)

The router address used by a device to communicate with networks outside its local subnet.

If a destination IP is not in the same subnet, the packet is sent to the gateway.

### Router

A Layer 3 network device that forwards packets between different networks based on IP addressing and routing tables.

Routers allow communication between different networks or subnets.

### Switch

A Layer 2 network device that connects devices inside the same local network (LAN). It forwards frames using MAC addresses.

Switches do not route between networks.

---

## CIDR Notation Quick Reference

| CIDR | Subnet Mask | Hosts per Subnet | Block Size |
| :---: | :---: | :---: | :---: |
| /24 | 255.255.255.0 | 254 | 256 |
| /25 | 255.255.255.128 | 126 | 128 |
| /26 | 255.255.255.192 | 62 | 64 |
| /27 | 255.255.255.224 | 30 | 32 |
| /28 | 255.255.255.240 | 14 | 16 |
| /29 | 255.255.255.248 | 6 | 8 |
| /30 | 255.255.255.252 | 2 | 4 |

`Hosts per subnet = 2^(host bits) − 2`

The two removed addresses correspond to:
- the network address
- the broadcast address

---

## Subnet Calculation Example

### Example 

Determine the network information for the IP address:

`192.168.1.34/26`

1. Convert the CIDR mask:

    /26 means that 26 bits belong to the network part.

    Binary subnet mask:

    `11111111.11111111.11111111.11000000`

    Decimal form:

    `255.255.255.192`

2. Calculate the subnet size using the Basic Calculator:

    `echo "256-192" | bc`

    Result:

    256 - 192 = 64
    
    Each subnet increases by 64.

3. Determine subnet ranges

    `0   - 63`
    `64  - 127`
    `128 - 191`
    `192 - 255`

    The IP 192.168.1.34 falls within:

    `192.168.1.0 - 192.168.1.63`

4. Determine network information:

    Network address

    `192.168.1.0`

    Broadcast address

    `192.168.1.63`

    Valid host range

    `192.168.1.1 - 192.168.1.62`

5. Binary verification using `bc`:

    Example:

    `echo "obase=2;192" | bc`

    This helps visualize the network and host bits while learning subnetting.

---

## Common Mistakes

Some common configuration errors that prevent network communication:

- IP address outside the subnet range
- Incorrect subnet mask
- Default gateway not in the same network as the device
- Using the broadcast address as a host
- Using the network address as a host
- Devices placed in different subnets without a router between them

---

## What I Learned

- How to calculate valid IP ranges using subnet masks.
- How to calculate subnet boundaries using CIDR notation.
- How to determine whether two devices belong to the same network.
- How to determine valid host ranges and broadcast addresses.
- Why a correct default gateway is required for inter-network communication.
- How routing allows communication between different subnets.
- How misconfigured IP addresses prevent network communication.

---

## Resources

To complete this project, I reviewed the following networking concepts:

- TCP/IP addressing
- IPv4 subnetting and CIDR notation 
- Subnet masks
- Broadcast addresses
- Default gateway configuration
- Router and switch roles in a network
- Basic OSI model structure

AI tools were used to clarify subnetting concepts and verify logical reasoning. All final configurations were solved manually and fully understood before submission.
