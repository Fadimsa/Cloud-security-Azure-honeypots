# cloud-security-azure-honeypots

## 
The Azure honeypot deployment lab where I created intentionally vulnerable VMs with open network access. Followed complete Azure workflow from resource group creation through NSG configuration with "all ports open" rule and RDP access setup.

------------------------------------------------------------------------------------------------------
## Skills Learned :- 

Azure resource group management and VM deployment workflow

Network Security Group (NSG) configuration for honeypot exposure

Windows VM administrator account and RDP access configuration

Firewall profile disabling for maximum attack surface exposure

Public IP connectivity testing and remote access validation
------------------------------------------------------------------------------------------------------
## Tools Used

Azure Portal - Complete cloud resource management

Azure Virtual Machines - Vulnerable Windows 10 honeypot instances

Network Security Groups - Custom inbound firewall rules

Remote Desktop (RDP) - VM remote administration access

Windows Defender Firewall - Profile configuration management
-----------------------------------------------------------------------------------------------------
## Steps taken : 

**1. Azure VM Creation Process**
- Navigated to "Create a resource" → Virtual Machine → "Create"
-  <img width="668" height="655" alt="image" src="https://github.com/user-attachments/assets/21d58913-c524-45bf-ab45-be5050d3d9a9" />

- Established new resource group for honeypot project organization and  Selected Windows 10 x64 image with custom VM naming and East US region
- <img width="720" height="660" alt="image" src="https://github.com/user-attachments/assets/25cf4988-496c-4c67-b7f0-32458bde46eb" />


**2. Administrator Account Configuration**
- Created local administrator credentials for RDP access
- Set inbound ports to "Allow selected ports" for RDP connectivity
- Enabled licensing agreement and progressed to networking tab
- <img width="712" height="663" alt="image" src="https://github.com/user-attachments/assets/92e742da-d52a-4ded-9768-48b06a6e1dc1" />


**3. Vulnerable NSG Configuration**
- Created new Network Security Group with advanced settings
- <img width="997" height="672" alt="image" src="https://github.com/user-attachments/assets/c699b5bd-92fe-4bf8-9250-c574fb9bfa1e" />

- Configured Destination Port Ranges: `*` (all ports), Priority: 100, Allow All
- <img width="998" height="657" alt="image" src="https://github.com/user-attachments/assets/d44b7b0c-75cb-44eb-9cb4-1809d0e9510c" />
- Deleted default inbound rule and added "DANGER_ANY_IN" rule
- <img width="1180" height="623" alt="image" src="https://github.com/user-attachments/assets/27774721-dbd8-4eaf-bbb8-5f7ad1ff560d" />




**4. VM Deployment & Public IP Assignment**
- Completed VM creation process (took ~5 minutes to provision)
- Verified "Running" status and retrieved Public IP from Overview tab

**5. RDP Remote Access Setup**
- Used Public IP address with created admin credentials
- Connected via Windows RDP client (or Microsoft Remote Desktop on Mac)
- <img width="1263" height="706" alt="image" src="https://github.com/user-attachments/assets/7250191a-b746-4d9e-97e9-a77788c76225" />

- Accepted "Remote computer cannot be verified" security warning

**6. Network Connectivity Testing**
- Ping test failed initially due to Windows firewall restrictions (icmp)
- <img width="708" height="421" alt="image" src="https://github.com/user-attachments/assets/835a9c7f-0320-4eed-a4e1-125c9b910508" />

- Accessed wf.msc → Disabled Domain/Private/Public firewall profiles (for testing purposes i closed all inbound and outbound firewall rules)
- Re-tested ping connectivity - successful responses confirmed
<img width="708" height="422" alt="image" src="https://github.com/user-attachments/assets/e5f678e4-3d58-4421-aef8-a19d1e177df9" />

**Findings Summary**: Successfully deployed fully-exposed Azure honeypot VM with all-ports NSG rule. Verified RDP access and network reachability. Ready for attack monitoring and security analysis.

## for the record 
closing and deleting the VM after finishing it would be best choice to aviod bill no one would like to pay !!

