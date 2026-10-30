# NETWORKWALKS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP

## 1. Introduction

Practical experience is an essential part of developing cybersecurity skills. Understanding security concepts theoretically is not enough; it is equally important to have a dedicated environment where different tools, configurations, and security techniques can be explored safely.

As the first step in building my cybersecurity laboratory, I installed **Kali Linux inside Oracle VM VirtualBox**. The purpose was to establish a virtual environment that could be used for Linux administration, network analysis, security testing, and future penetration-testing exercises.

Running Kali Linux as a virtual machine provides flexibility and isolation from the host operating system. It also makes it easier to manage system configurations, take snapshots, and experiment without modifying the physical computer's operating system.

This project documents the initial setup, virtualization configuration, network connectivity, and verification process.


## 4. System and Software Requirements

The following components were used to establish the laboratory:

| Component | Description |
|---|---|
| Host OS | Windows |
| Virtualization Software | Oracle VM VirtualBox |
| Guest OS | Kali Linux |
| Installation Method | ISO-based installation |
| Virtual Network Adapter | VirtualBox virtual NIC |
| Network Mode | NAT |
| Internet Access | Through host network connection |

The virtual machine uses allocated virtual hardware resources, including RAM, virtual CPU cores, and virtual disk storage. These resources are managed by VirtualBox and shared with the host system.

## 5. Implementation and Configuration

### 5.1. VirtualBox Installation

Oracle VM VirtualBox was installed as the virtualization platform.

VirtualBox allows multiple operating systems to run independently on the same physical computer. It provides virtual hardware components such as processors, memory, storage controllers, and network adapters.

For this laboratory, VirtualBox was selected because it is accessible, flexible, and suitable for creating isolated cybersecurity environments.

### 5.2. Kali Linux Installation

Kali Linux was installed as a guest operating system inside a newly created virtual machine.

The installation process involved:

1. Creating a new virtual machine.
2. Selecting Linux as the operating system type.
3. Allocating virtual memory and processor resources.
4. Creating virtual disk storage.
5. Attaching the Kali Linux installation ISO.
6. Completing the operating system installation.
7. Booting into the installed Kali Linux environment.

After installation, the virtual machine successfully started and provided access to the Kali Linux desktop environment.

### 5.3. Virtual Machine Network Configuration

Network connectivity is an important part of a cybersecurity laboratory because many security tools require access to external repositories, updates, and network services.

For this setup, the virtual network adapter was configured in **NAT (Network Address Translation)** mode.

NAT allows the guest operating system to access external networks using the host computer's network connection.

The main advantages of this configuration include:

- Internet connectivity without requiring a separate physical network interface.
- Reduced direct exposure of the guest machine to the external network.
- Simplified network configuration.
- A suitable starting point for learning Linux networking.

One important consideration is that NAT does not automatically make the virtual machine completely isolated or secure. Additional network controls may be required when creating advanced security laboratories.

## 6. Network Connectivity Verification

After configuring the virtual network adapter, connectivity was tested from the Kali Linux terminal.

The purpose of this testing was to verify that the virtual machine could communicate with external IP addresses and resolve domain names.

### 6.1. Checking Network Interfaces

The following command was used to inspect the available network interfaces and their IP configurations:

```bash
ip addr
```

This command displays network interfaces, assigned IP addresses, and interface states.

The default network interface should have an IP address assigned by the VirtualBox NAT environment.

### 6.2. Testing External IP Connectivity

To verify basic connectivity with an external IP address, the following command was used:

```bash
ping -c 4 8.8.8.8
```

Google Public DNS (8.8.8.8) was used as the destination for this connectivity test.

Successful replies indicate that ICMP communication with the destination is working.

### 6.3. Testing DNS Resolution

IP connectivity alone does not confirm that DNS is functioning correctly.

To test domain name resolution, the following command can be executed:

```bash
ping -c 4 google.com
```

This test checks whether Kali Linux can resolve a domain name into an IP address and communicate with the resolved destination.

Another useful command is:

```bash
nslookup google.com
```

This provides information about the DNS server used and the resolved IP addresses.

### 6.4. Internet Connectivity Test

**Testing the connectivity of Kali Linux to the Internet**

[Insert the terminal screenshot showing successful internet connectivity here.]

The connectivity verification process helps distinguish between basic IP connectivity and DNS resolution issues. This distinction is particularly important when troubleshooting virtual network environments.

## 7. Technical Observations

During the initial setup, several networking concepts became particularly relevant:

**Virtualization:** VirtualBox provides virtual hardware that allows Kali Linux to operate independently of the host operating system.

**NAT:** Network Address Translation enables the guest machine to access external networks through the host's network connection.

**IP Connectivity:** Successful communication with an external IP address indicates that basic network-layer connectivity is available.

**DNS Resolution:** DNS translates human-readable domain names into IP addresses. A system may have working IP connectivity while still experiencing DNS resolution failures.

These concepts provide a foundation for understanding more advanced networking and cybersecurity configurations.

## 8. Security Considerations

Although this is an initial learning environment, security should be considered from the beginning.

The following practices are recommended:

- Keep Kali Linux and installed packages updated.
- Use strong authentication credentials.
- Avoid running unnecessary network services.
- Take virtual machine snapshots before major configuration changes.
- Use isolated or host-only networks for controlled experiments involving vulnerable machines.
- Perform scanning and security testing only against systems for which authorization has been obtained.
- Avoid exposing vulnerable lab services directly to public networks.

The NAT configuration used in this project provides a convenient starting point, but it should not be treated as a complete security boundary.

## 9. Challenges and Troubleshooting

Network connectivity and DNS configuration are common areas that require attention when setting up Linux virtual machines.

For example, if Kali Linux can successfully ping an external IP address but cannot resolve a domain such as `google.com`, the problem may be related to DNS configuration rather than general internet connectivity.

A systematic troubleshooting approach should include:

1. Checking whether the virtual network interface is active.
2. Verifying that the machine has received a valid IP address.
3. Checking the default routing configuration.
4. Testing connectivity using an external IP address.
5. Inspecting DNS configuration.
6. Testing domain resolution independently.

Useful commands include:

```bash
ip addr
ip route
ping -c 4 8.8.8.8
cat /etc/resolv.conf
nslookup google.com
```

This approach helps identify whether the problem exists at the interface, routing, or DNS layer.

## 10. Future Development

This laboratory is intended to serve as the foundation for more advanced cybersecurity exercises.

The next stages of development will focus on:

- Linux system administration and command-line proficiency.
- Network discovery and reconnaissance using Nmap.
- Network traffic analysis using Wireshark.
- Understanding TCP/IP protocols and common network services.
- Vulnerability assessment in controlled environments.
- Building isolated attack-and-defense lab topologies.
- Exploring penetration-testing methodologies and security tools.
- Developing practical knowledge of network security and system hardening.

As the laboratory develops, additional machines and network segments may be introduced to simulate realistic environments.

## 11. Conclusion

The initial setup of the Kali Linux virtual laboratory was an important first step toward developing a practical cybersecurity environment.

By installing Kali Linux inside Oracle VirtualBox and configuring its virtual network adapter, I established a foundation for experimenting with Linux, networking, and security-related technologies.

Beyond the installation itself, this project provided practical exposure to virtualization, virtual networking, NAT, IP connectivity, and DNS resolution.

The environment will be expanded gradually as I continue developing my knowledge and practical skills in network engineering and cybersecurity.

---

## References

- [Kali Linux Official Documentation](https://www.kali.org/docs/)
- [Kali Linux Official Website](https://www.kali.org/)
- [Oracle VM VirtualBox Documentation](https://www.virtualbox.org/manual/)
- [Google Public DNS](https://developers.google.com/speed/public-dns)

---

**Author:** Murtaza Mehreyar  
**Project:** Kali Linux Virtual Lab Setup  
**Domain:** Cybersecurity | Network Engineering | Linux Administration

*This project is part of my ongoing practical learning journey in cybersecurity. The laboratory will be updated as new configurations, experiments, and security exercises are completed.*
