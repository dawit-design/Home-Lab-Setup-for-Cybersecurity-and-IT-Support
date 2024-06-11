# Home Lab Setup for Cybersecurity and IT Support
## Objective
To simulate an enterprise network environment to demonstrate my IT support and cybersecurity skills.

# Table of Contents
1. Virtualization Setup
2. Network Configuration
3. Server and Client Management
4. Network Services
5. Cybersecurity Practices
6. 7Troubleshooting Scenarios
7. Conclusion

# Prerequisites
- Hardware: A computer with at least 16 GB of RAM and 500 GB of free disk space.
- Software:
   - VirtualBox
   - VirtualBox Extension Pack
   - Windows Server ISO
   - Windows 10 ISO

# 1. Virtualization Setup
## Tools
- VirtualBox: [Download here](https://www.virtualbox.org/wiki/Downloads)
- VirtualBox Extension Pack: [Download here](https://www.virtualbox.org/wiki/Downloads)
## Virtual Machines
- Windows Server 2019
- Windows 10
  
## Configuration
## 1. Installed VirtualBox Workstation:
   - Installed VirtualBox and Extension Pack.
   - I followed the installation instructions for both VirtualBox and the Extension Pack.
   - Example screenshot:
     ![VM VirtualBox Installation](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/2015d127-d640-4c6e-ad74-172252c25cdf)

## 2. Creating Virtual Machines:
## Steps:
   1. Opened VirtualBox and click 'New'.
      - Named my VM (e.g., Domain Controller(DC), selected the type (Microsoft Windows), and version (Other (64-bit)).
      - Example screenshot:
      ![Create a Windows Server VM](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/9f196fe5-627f-4f54-9094-db9e1ed393a3)
     ![Windows server installation done](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/3f308de0-b8d8-474f-8210-da9ecac3e86d)
     ![Windows Server Installation2](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/8c9d9c12-81e7-46fb-a948-7a37622ec755)
     ![Windows Server Installation3](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/1de7f303-c2d2-4c67-8614-8a4a2b6b4988)
   2. Allocated resources.
      - Assigned at least 2 GB RAM, 2 CPUs, and 20 GB of disk space.
      - Example screenshot:
     ![Assign 2gb RAM and 2CPUs for Windows Server VM](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/f48d38e4-9338-4bec-9466-af5164d681a2)
      - Example screenshot:
  ![20GB hard disk assigned](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/2ec9e85c-2a11-4250-8b9a-a4d98e3e39ee)
   3. Configured the network.
      - Used NAT Adapter for external network access and Internal Network for internal communication.

# 2. Network Configuration
## NIC Setup
   1. NAT.
      - This provides internet access to the VMs.
   2. Internal Network Adapter.
      - Used for communication between VMs.
## Configuration Steps
## 1. Assign NICs to VMs:
   - I went to Settings > Network in VirtualBox and set Adapter 1 to NAT and Adapter 2 to Internal Network.
   - Example screenshot:
   ![Internal Netowrk Adapter](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/352f5421-3b67-4812-be32-0d6659a607dd)

## 2. Configure DHCP Server on Windows Server 2019:
   - I installed the DHCP role via Server Manager.
   - Created a new scope with IP range: 172.16.0.100-172.16.0.200.
   - Example screenshot:
  ![DHCP Config](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/94ed71d5-5085-4fa7-a379-f1a58f6a79ef)
  ![DHCP Config done](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/9bf6baf0-a0af-44b7-a750-ef92d304c463)
  ![Setting A scope](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/ce02cc2d-3677-41cf-a6c5-288aaf6815aa)


# 3. Server and Client Management
## Operating Systems
      - Windows Server 2019: Used for Active Directory Domain Services (AD DS).
- Windows 10: Client/User machines for testing.
## Configuration Steps
## 1. Installed Windows Server:
   - I followed the installation prompts, configured basic settings, and set a static IP for the Internal NIC.
## 2. Installed Winodws 10
   - Set up two Windows 10 VMs as client machines.
   - Example screenshot:
     ![Windows 10 Installation](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/dece6e31-3be7-471a-b25d-9cd3bc61f9a1)
     ![Windows 10 install1](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/53572e28-dee9-41ce-a02d-54389ba85ed8)
     ![Windows 10 install2](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/1d9e540c-7472-4fc3-a10c-46fc057bc226)

  
## 2. Set Up Active Directory on Windows Server:
## - Install AD DS Role:
   - I opened 'Server Manager', and added 'Active Directory Domain Services'.
   - Clicked on "Add roles and features" and proceeded with the installation.
   - Example screenshot:
     ![AD Installation2](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/e0ca0d6b-d1a6-4c24-bd58-561140c63e0a)
## - Promote Server to Domain Controller:
   - Set DNS to the server’s internal IP and joined the domain via System Properties.
   - I followed the wizard to create a new forest with the domain name highfive.com.
   - Completed the promotion process and restarted the server.
   - Example screenshot:
     ![New forest   Domain Installation](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/5611814b-f87e-442e-a93f-5eb4b4c6d1ef)

     
## 3. Create User Accounts:
   - I opened "Active Directory Users and Computers" on the Windows Server 2019 VM.
   - Navigated to the domain highfive.com, right-clicked on "Users", and selected "New" > "User".
   - Created user accounts (e.g., user1@highfive.com, dendaylalu@highfive.com).
   - Example screenshot:
     ![new user created](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/21d6b290-42c8-4b43-b512-c1cc28ec6bdc)

     
## 4. Apply Group Policies:
   - I opened "Group Policy Management" on the Windows Server 2019 VM.
   - Created a new Group Policy Object (GPO) and linked it to the domain highfive.com.
   - Configured policies for security and software installation.
   - Example screenshot: Sample Image (Label: Example)
     
# 4. Network Services
## RAS and NAT Configuration 
## Steps
   ## 1. Enable Routing and Remote Access Service (RAS):
   - I opened Server Manager, added a Remote Access role (RAS), and configured NAT.
   - Example screenshot:
     ![Install RAS ](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/b77b7e7c-2d19-483c-be6f-df3a3d4be893)
     ![Install RAS2](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/fddb15d7-f174-424e-bbb5-cad62307dae9)

  ##2. Configure NAT:
  - I set up NAT to allow internal VMs to access the internet.
  - Example screenshot:
    ![NAT INSTALLATION](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/2f3331f1-ccfb-4004-8cbe-42e11779aec5)

  ##3. Define DHCP Scope:
  - I ensured the DHCP scope was defined with the IP range 172.16.0.100-200.
  - Example screenshot:
    ![Setting A scope](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/e4976514-cf68-4ced-8a72-0fa2ce16a5f9)
    
# 5. Cybersecurity Practices
## Vulnerability Assessments
Tools: Kali Linux, Metasploit, Nmap, Wireshark

## Steps
## 1. Conduct Vulnerability Assessments:
   - Tools:
   - Nmap: Network scanning.
   - Metasploit: Exploitation framework.
   - Wireshark: Network traffic analysis.
## Using the Tools
   - Nmap: Ran basic scans (nmap -sP 192.168.1.0/24) to discover devices.
   - Example screenshot: Sample Image (Label: Example)
   - Metasploit: Performed a basic exploit (e.g., MS08-067).
   - Example screenshot: Sample Image (Label: Example)
   - Wireshark: Captured and analyzed traffic.
   - Example screenshot: Sample Image (Label: Example)

## DNS Configuration
## Steps
## 1. Set Up DNS on Windows Server:
   - I installed the DNS role via Server Manager on the Windows Server 2019 VM.
   - Configured DNS to resolve internal domain names securely.
   - Example screenshot: Sample Image (Label: Example)

## 2. Implement Secure DNS Settings:
   - I applied secure DNS settings to prevent spoofing attacks.
   - Example screenshot: Sample Image (Label: Example)
  
#6. Troubleshooting Scenarios
## Scenario 1: User Unable to Connect to Network
## Steps
## 1. Check NIC Settings:
   - Checked NIC settings and ensured proper configuration.
   - Verified IP settings using ipconfig /all.
   - Example screenshot: Sample Image (Label: Example)

## 2. Check DHCP Server Logs:
   - I ensured the DHCP server was assigning IP addresses correctly.
   - Example screenshot: Sample Image (Label: Example)

## 3. Resolve IP Conflict:
   - I identified and resolved any IP conflicts within the network.
   - Example screenshot: Sample Image (Label: Example)

## Scenario 2: Slow Network Performance
## Steps
## 1. Monitor Network with Wireshark:
   - Used Task Manager and Resource Monitor to check for high network usage.
   - Analyzed network traffic with Wireshark.
   - Example screenshot: Sample Image (Label: Example)

# Conclusion
This home lab project demonstrates my ability to set up, configure, and manage an enterprise-like network environment. It highlights my skills in troubleshooting, network management, and cybersecurity practices. The detailed documentation and hands-on practice underscore my readiness to tackle real-world IT support challenges.
