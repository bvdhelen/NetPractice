*This project has been created as part of the 42 curriculum by eldiaz-c*

# NetPractice

## Description

NetPractice is a practical networking project focused on understanding the fundamental of TCP/IP addressing and basic network configuration.

The objetive of this project is to correctly configure small-scale networks by assigning valid IP addresses, subnet masks and default gateways in order to make the network functional or to restore communication between devices.

The project consists of 10 levels of increasing difficulty. Each level presents a non-functioning network diagram that must be fixed by adjusting the available configuration fields by analyzing addressing, identifying subnet boundaries, and ensuring proper routing between networks.

Through this project, I developed a deeper understanding of how devices communicate within a network and how routing works between different subnets (logical reasoning, subnet calculation, routing...).

---

## Instructions

1. Download the project files from the NetPractice page.
2. Extract the files into a local directory.
3. Open the `index.html` file in a web browser.
4. Enter your login to generate your personal configuration.
5. Solve each of the 10 levels by correcting the network configuration.
6. After completing a level, click on **Get my config** to export the configuration file.
7. Place the 10 exported configuration files (one per level) at the root of your Git repository before submission.

During evaluation, three random levels must be solved within a limited time. External tools are not allowed (only simple calculation tools such as `bc` are tolerated).

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
- Switch role in local network commumication
- Communication between different subnets (inter-subnet routing)
- Basic understanding of OSI layers (Layer 2 vs Layer 3 responsabilities)

---

## Subnet Calculation Example

Example use of the Basic Calculation:

`echo "256-128" | bc`

`echo "obase=2;128" | bc`

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

To complete this project, I reviewed the following concepts:

- TCP/IP addressing
- IPv4 subnetting and CIDR
- Default gateway configuration
- Router and switch roles in a network
- Basic OSI model structure

AI tools were used to clarify subnetting theory and verify logical reasoning. All final configurations were solved manually and fully understood before submission.
