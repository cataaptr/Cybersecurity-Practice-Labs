# 🔐 Cybersecurity-Practice-Labs
In this repository, I will document all the tools I learn throughout my cybersecurity journey, hoping it may also be useful for others.

## ✅ Setup Components:
1. **VMware (or other virtualization platforms, e.g., VirtualBox)**
- *Description*: VMware or VirtualBox provides the virtualized environment needed for setting up and running different OS instances safely.
- *Recommended Video*: [How to Install Windows 11 on VMware](https://www.youtube.com/watch?v=pRYCUaUBuUs&t=260s)

2. **Kali Linux Purple**
- *Description*: Kali Linux Purple is a specialized distribution tailored for cybersecurity professionals, offering pre-installed tools for both offensive and defensive security.
- *Recommended Video*: [How To Install Kali Linux Purple 2023.1](https://www.youtube.com/watch?v=ZR35g8AWebc&t=1052s)
                   [Install Kali Purple In VMWare Workstation 17](https://www.youtube.com/watch?v=fpzn3dSBgcI)
                   [Install Kali Linux Purple on a VMware](https://www.youtube.com/watch?v=O2xtREUgJnw&t=478s)

3. **Metasploitable 2**
- *Description*: Metasploitable 2 is a vulnerable virtual machine used for practice in penetration testing.
- *Recommended Video*: [How to install and Configure Metasploit on Kali Linux 2022](https://www.youtube.com/watch?v=DKWDx70cAnU&t=120s)
                   [install Kali Linux 2024.1 & Metasploitable2 on VirtualBox 7 Step By Step : Cyber Security Lab 2024](https://www.youtube.com/watch?v=yf3jetn4tN8&t=211s)

## Network Configuration

- Ensure that both **Kali Linux** and **Metasploitable 2** are on the same virtual network. You can test the connectivity between the two machines using the `ping` command.
- Recommended Site: [How to Link Kali Linux with Metasploitable 2](https://www.geeksforgeeks.org/how-to-link-kali-linux-with-metasploitable-2/)

1. **Check IP Address on Kali Linux**:
   - Open a terminal on **Kali Linux** and run the following command to find the IP address assigned to your Kali machine:
     ```bash
     ifconfig
     ```
   - The `ifconfig` command displays the network configuration details for your network interfaces, including the IP address. Look for the section labeled `eth0` (or similar) and find the `inet addr` line, which shows your machine's IP address.

2. **Testing Connectivity**:
   - Once you have the IP address of your Metasploitable machine, you can test the connectivity between the two machines using the `ping` command:
     ```bash
     ping [IP address of Metasploitable]
     ```
   - Replace `[IP address of Metasploitable]` with the actual IP address assigned to your Metasploitable machine.
   - The `ping` command sends ICMP Echo Request packets to the specified IP address and waits for a reply. A successful ping response (e.g., `64 bytes from [IP address]: icmp_seq=1 ttl=64 time=0.123 ms`) indicates that the machines can communicate with each other.

