# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
Building an isolated virtual lab for penetration testing and ethical hacking practice.

PROJECT OVERVIEW

This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

🎯 OBJECTIVES

-The main objectives of this project are to:

-Install and configure VirtualBox.

-Install/import Kali Linux as a virtual machine.

-Create a private NAT Network for the cybersecurity lab.

-Configure network connectivity for Kali Linux.

-Assign a consistent IP address to the Kali VM.

-Verify network connectivity and DNS resolution.

-Take a clean VM snapshot for recovery.

-Document the complete setup process.

-Prepare the environment for future cybersecurity projects.

🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Exploitation practice
Security-tool experimentation

LAB ARCHITECTURE

<img width="666" height="316" alt="Screenshot 2026-09-10 215145" src="https://github.com/user-attachments/assets/45454020-2998-4ebb-ae45-73eb1bcefcb8" />

 Lab Configuration

 <img width="250" height="358" alt="Screenshot 2026-09-10 230850" src="https://github.com/user-attachments/assets/246f6db7-9e66-4718-aca4-45e32c1d1c66" />


🪜 Lab Setup Procedure

Step 1. Install 7-Zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive.

Tool: 7-Zip

Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled

<img width="612" height="431" alt="Screenshot 2026-09-10 220723" src="https://github.com/user-attachments/assets/43c04f9b-7fa5-4432-bd7d-97a67d327aed" />

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.

Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
The VM was allocated:

RAM: 2048 MB

<img width="639" height="418" alt="Screenshot 2026-09-10 000253" src="https://github.com/user-attachments/assets/6500a7fd-57db-4d62-8f7b-cfb6e1e41f94" />

Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

configuration:

IP Address:   10.0.0.2
Subnet Mask:  255.255.255.0
Gateway:      10.0.0.1
DNS:          8.8.8.8
A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<img width="360" height="279" alt="Screenshot 2026-09-10 002805" src="https://github.com/user-attachments/assets/33a20294-df4f-4ef6-9c6d-762b3a2e8068" />

Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

Clean Kali - Network Setup
The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

🔎 Lab Verification

<img width="548" height="194" alt="Screenshot 2026-09-10 230813" src="https://github.com/user-attachments/assets/d5dc5474-62db-45fe-878e-09b1f10e54a3" />

IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8

🐞 Problems Encountered & Solutions

Problem 1. kali Linux Incomplete Download
During Kali Linux Download, the zip file keeps getting stuck indicating 0 B/s - 3.7 GB of 3.7GB but showing incomplete download in the folder. I deleted my old version of Kali Linux in the system thinking that was the cause but the problem persisted.

Solution:
I cleared every previous downloads, restarted the system and started a new download. When it got to the 100MB left to download, i simply paused the download, started, paused again until the download reach the finish notification.

Problem 2. Internet Connectivity After Static IP Configuration
After manually configuring the IPv4 settings, i tried testing the internet connection by searching google.com webpage, Google page opened and displayed, i went ahead to search for network walks on the search bar but the connection was lost.

Solution:
I typed the command in the terminal;

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

The network connection was then restarted/rebooted and connectivity was tested again. problem solved

💡 What I Learned
Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

1. NAT vs NAT Network
2. 
A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

2. Virtual Machine Networking
3. 
I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

4. Static IP Configuration
5. 
I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

6. VM Snapshots
I learned that a clean snapshot should be created before performing risky or experimental activities.

7. Documentation
   
I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

🔗 Tools & Resources

7-Zip: https://7-zip.org/download.html

VirtualBox: https://virtualbox.org/wiki/Downloads

Kali Linux: https://kali.org/get-kali

👤 Author
Idongesit Nkanga

Cybersecurity Intern B083

LinkedIn: https://www.linkedin.com/in/idongesit-george-7b0125a8 

📌 Project Information

Program Name: Cybersecurity at Networkwalks | Week: 01 | 

Project: Cybersecurity & Pentesting Lab Setup | Repository: GitHub


