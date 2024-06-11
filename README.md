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
   
# 1. Virtualization Setup
## Tools
- VirtualBox
## Virtual Machines
- Windows Server 2019
- Windows 10
- Configuration
  
Each VM is configured with:
- RAM: 2GB
- CPUs: 2
- Hard Drive: 20GB
  
## Steps
## 1. Install VMware Workstation:
- I downloaded and installed VirtualBox Workstation from the official website.
- Example screenshot: ![VM VirtualBox Installation](https://github.com/dawit-design/Home-Lab-Setup-for-Cybersecurity-and-IT-Support/assets/71353146/2015d127-d640-4c6e-ad74-172252c25cdf)

  
## 2. Create Virtual Machines:
- I opened VMware Workstation.
- Clicked on "Create a New Virtual Machine".
- Followed the wizard to install the operating systems.
- Example screenshot: Sample Image (Label: Example)
  
## 3. Configure Virtual Machines:
- I allocated 2GB RAM and 2 CPUs for each VM.
- Set the hard drive size to 20GB.
- Example screenshot: Sample Image (Label: Example)
  
# 2. Network Configuration
## NIC Setup
- NIC 1: Internal network communication
- NIC 2: Internet access
## Steps
## 1. Assign NICs to VMs:
- I went to the VM settings.
- Added two network adapters: one for internal and one for internet access.
- Example screenshot: Sample Image (Label: Example)
  
## 2. Configure DHCP Server on Windows Server 2019:
- I installed the DHCP role via Server Manager.
- Created a new scope with IP range: 172.16.0.100-172.16.0.200.
- Example screenshot: Sample Image (Label: Example)
  
# 3. Server and Client Management
## Operating Systems
- Windows Server 2019 with Active Directory Domain Services (AD DS)
- Windows 10 for end-user testing
## Steps
## 1. Deploy Operating Systems:
   - I installed Windows Server 2019 on one VM and Windows 10 on the other.
   - Example screenshot: Sample Image (Label: Example)
  
## 2. Set Up Active Directory on Windows Server:
## - Install AD DS Role:
   - I opened Server Manager on the Windows Server 2019 VM.
   - Clicked on "Add roles and features".
   - Selected "Active Directory Domain Services" and proceeded with the installation.
   - Example screenshot: Sample Image (Label: Example)
## - Promote Server to Domain Controller:
   - After installing AD DS, a notification appeared to promote the server to a domain controller.
   - I followed the wizard to create a new forest with the domain name example.local.
   - Completed the promotion process and restarted the server.
   - Example screenshot: Sample Image (Label: Example)
     
## 3. Create User Accounts:
   - I opened "Active Directory Users and Computers" on the Windows Server 2019 VM.
   - Navigated to the domain example.local, right-clicked on "Users", and selected "New" > "User".
   - Created user accounts (e.g., user1@example.local, admin@example.local).
   - Example screenshot: Sample Image (Label: Example)
     
## 4. Apply Group Policies:
   - I opened "Group Policy Management" on the Windows Server 2019 VM.
   - Created a new Group Policy Object (GPO) and linked it to the domain example.local.
   - Configured policies for security and software installation.
   - Example screenshot: Sample Image (Label: Example)
     
# 4. Network Services
## RAS and NAT Configuration
## Steps
   ## 1. Enable Routing and Remote Access Service (RAS):
   - I opened Server Manager on the Windows Server 2019 VM.
   - Added the RAS role and configured it for NAT.
   - Example screenshot: Sample Image (Label: Example)
     
  ##2. Configure NAT:
  - I set up NAT to allow internal VMs to access the internet.
  - Example screenshot: Sample Image (Label: Example)

  ##3. Define DHCP Scope:
  - I ensured the DHCP scope was defined with the IP range 172.16.0.100-200.
  - Example screenshot: Sample Image (Label: Example)
    
# 5. Cybersecurity Practices
## Vulnerability Assessments
Tools: Kali Linux, Metasploit, Nmap, Wireshark

## Steps
## 1. Conduct Vulnerability Assessments:
- Nmap: I used Nmap on the Kali Linux VM to scan the network for open ports.
- Example screenshot: Sample Image (Label: Example)
- Metasploit: I performed penetration testing using Metasploit to exploit vulnerabilities.
- Example screenshot: Sample Image (Label: Example)
  
## 2. Monitor Network Traffic:
- Wireshark: I captured network traffic using Wireshark and analyzed it for suspicious activities.
- Example screenshot: Sample Image (Label: Example)

## DNS Configuration
## Steps
## 1. Set Up DNS on Windows Server:
- I installed the DNS role via Server Manager on the Windows Server 2019 VM.
-Configured DNS to resolve internal domain names securely.
-Example screenshot: Sample Image (Label: Example)

## 2. Implement Secure DNS Settings:
- I applied secure DNS settings to prevent spoofing attacks.
- Example screenshot: Sample Image (Label: Example)
  
#6. Troubleshooting Scenarios
## Scenario 1: User Unable to Connect to Network
## Steps
## 1. Check NIC Settings:
- I verified the NIC configuration on the VM.
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
- I captured and analyzed network traffic.
- Example screenshot: Sample Image (Label: Example)

## 2. Identify Bandwidth-Hogging Applications:
- I pinpointed applications consuming excessive bandwidth.
- Example screenshot: Sample Image (Label: Example)

## 3. Mitigate Performance Issue:
- I took appropriate actions to mitigate the issue.
- Example screenshot: Sample Image (Label: Example)

# Conclusion
This home lab project demonstrates my ability to set up, configure, and manage an enterprise-like network environment. It highlights my skills in troubleshooting, network management, and cybersecurity practices. The detailed documentation and hands-on practice underscore my readiness to tackle real-world IT support challenges.
