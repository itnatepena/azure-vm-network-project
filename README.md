# Azure Virtual Machine Network Inspection Project

This project guides you in setting up two Virtual Machines (VMs) one within the other, using the same network with Azure and inspecting network traffic between the two machines using Wireshark.

This project assumes you have a basic familiarity with Azure and have an Azure account.

## Getting Started

### 1. Create a Resource Group and VM

1.1. Create a Resource Group: Using the Azure Portal's search bar, create a resource group. Ensure that you select a Windows 10 image and provide a username and password for your Administrative account on the Virtual Machine (VM). Make sure the VM is within your resource group and click "Create."

### ![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/76d48a31-ea3c-436d-a694-b596f5b577b1)


### 2. Create the Second VM

2.1. Create Another VM: In Azure, go to your virtual machines and create a second VM. Ensure it is within the same Resource Group and contained within the virtual network (vnet) created in Step 1 for this lab to work.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/45a950a3-94f9-4737-b9e3-da3f2f465879)


### 3. Connect Remotely to VM1

3.1. Copy Public IP Address: Head to Virtual Machines on Azure using the search bar. Click on the first VM and copy the PUBLIC IP address.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/3ef6bbe0-8989-491d-8f1a-5c93b6efe934)


3.2. Connect via Remote Desktop: Open Remote Desktop Connection on your Windows PC, enter the copied IP address, connect, and input your username and password credentials.

### 4. Install Wireshark on VM1

Download and install Wireshark within VM1. (Provide a brief explanation of why you are using Wireshark for this project)


### 5. Obtain the Private IP from VM2

Get the PRIVATE IP from VM2. Copy and paste both the Private IP addresses YOU MADE as you will be using them multiple times in this project. (Yours may be different from mine)

- VM1: 10.0.0.4
- VM2: 10.0.0.5

5.1. Connect to VM2: Use VM2's PUBLIC IP address to connect to VM2 from VM1 via Remote Desktop Connection.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/cffd1a9d-8871-40e1-ad1c-ed01626dc125)


### 6. Explore the Environment

Explore your environment, create a PowerShell session on VM2 and a CMD prompt on VM1(this makes it easy to see the difference). You can ping VM1 from VM2 and vice versa. Observe what happens when you run commands such as "whoami."

### 7. Troubleshooting Network Issues

Both VMs may experience "requests timed out" when trying to ping each other. You can check connectivity by pinging google.com to verify network connectivity. Explore potential issues related to firewalls blocking virtual machine traffic.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/7fc9f1c4-aee2-45f5-927f-fed473eea785)

We can try Pinging Google, and/or a loopback address(127.0.0.1) to confirm our TCP/IP is working.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/c9d35c1f-ef75-4917-bed0-7d009600bedb)

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/ee8e5ae4-a669-4264-a3e8-109cc77e49bc)


### 8. Enable Communication

To Enable communication between VM1 and VM2, you will ahve to configuring firewall settings or disable the firewall temporarily. This is essential to establish network communication in this Project and is fine for our uses, and future uses. 
IMPORTANT NOTE: It is generally not a good idea to leave a firewall disabled, especially in sensitive circumstances. For security reasons, consider re-enabling the firewall or configuring it to allow specific traffic when you're done with this project.

### 9. Inspect Traffic with Wireshark

With communication enabled, you can send and receive pings between VM1 and VM2 now. Use Wireshark to inspect network traffic. Filter Wireshark for ICMP traffic to see how the two VMs communicate.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/26ca90db-795a-46ed-9e3d-4a72b0d218d5)

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/515f518e-5fe8-4da4-9d86-9fe1fa1e86f6)



## Conclusion

This project creates an isolated environment for testing and educational purposes. Virtual machines within virtual machines are not a common practice but can be useful for creating controlled test environments for various purposes. I wanted to emphasize that disabling a firewall can be considered bad practice, and rather we should be allowing specific traffic through using the Azure Portal. This project also provides a visual representation of how VMs and cloud services work together to create new environments and demonstrates their ability to interact with each other.

![image](https://github.com/itnatepena/azure-network-protocols/assets/147539410/fff184d8-b68d-497b-9818-70ab02f0391b)


This README serves as a guide to set up and explore this environment. Feel free to modify and expand upon this project to meet your specific testing and educational needs.

For more information and resources related to Azure and virtual machine networking, refer to Azure's documentation and resources.

**I plan to revise this to include the proper security settings avaialble in the Azure Portal for allowing communication between VM1 and VM2. This was simply a demonstration, without any major purpose.
