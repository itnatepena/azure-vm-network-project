# Azure VM Connectivity and File Sharing Lab

## Introduction

This project aims to provide a comprehensive demonstration of the process involving the creation of two Azure virtual machines (VMs), the testing of ICMPv4 connectivity between these VMs, capturing network traffic with Wireshark, sharing documents between VMs, modifying and resharing documents, and ultimately transferring a file to a local desktop.

## Prerequisites

- Microsoft Azure
- Azure Data Studio

## Step 1: Create Azure Virtual Machines

1. Log in to your Azure portal.
2. Create two Windows 10 Azure VMs (WIN1 and WIN2) within the same Azure Virtual Network and subnet.
![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/3b8ac766-ee1b-4d80-8414-a81db0fb9177)


## Step 2: Allow ICMPv4 Addresses

1. Configure Network Security Group (NSG) rules or firewall rules to allow ICMP (ping) traffic between VM1 and VM2.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/8179e4a3-2f9b-4e52-8e49-6eef30e030b3)
*Note: Its better to configure network-wide security configurations from the azure portal. You want to execute changes at top level so it trickles down to your Virtual Machines. This is best practice.

## Step 3: Test ICMPv4 Connectivity

1. Connect to VM1 and use the Command Prompt to ping VM2. Ensure successful ICMPv4 connectivity.
2. Similarly, connect to VM2 and ping VM1.

First we see a failed ping from WIN1 to WIN2, followed by the ICMPv4 allowance, we can see succesfful pings.
![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/1f3826a3-5e9a-4eb5-baca-16e772d0dcd3)

Here is WIN2 Pinging WIN1
![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/5f21fc1c-cf3f-4bda-bc43-c43e58d1bc04)


## Step 4: Install Wireshark on VM1

1. Download and install Wireshark on VM1 to capture network traffic.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/4452b53b-a660-4a3a-8202-0da3902cdcbe)


## Step 5: Test Connectivity and View in Wireshark

1. Start a packet capture in Wireshark on VM1.
2. On VM2, ping VM1 and observe the captured ICMPv4 packets in Wireshark.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/fdb355e0-91b4-4ce8-8152-5603fde4b432)


## Step 6: Create a Shareable Document

1. On VM1 (also known as Win1), create a document that you want to share between VMs.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/09d22bc5-43ce-4e15-9c20-2da65228f96f)

Here we created a simple txt document to share with VM2(WIN2)


## Step 7: Share the Document

1. Share the document on Win1 and set it as shareable with specific user permissions. Apply the changes.


We set the permissions to "Everyone" for this project.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/d20fa554-b0b8-4837-b6dc-8a1b43982688)


## Step 8: Restart to Apply Settings

1. Restart VM1 to ensure that the inital document sharing settings take effect.

After setting permissions, I am able to view the document from VM2(WIN2)

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/d5659f42-29b1-4646-8d88-4d647644d92b)


## Step 9: Access VM1 (Win1) from VM2 (Win2)

1. On Win2 (VM2), navigate to Win1's shared resources using the path \\Win1\SharedFolderName.
   
![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/8ef0bf2a-a850-48e0-820b-9fd047fe1fcc)


## Step 10: Transfer the Document to Local Desktop

1. Copy the shared document from Win1 to your local desktop (the desktop of the machine you are using to access VMs).

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/791c465a-6e21-436d-88f1-60902993f22f)


## Step 11: Modify and Reshare the Document

1. Modify the document locally and reshare it from your local desktop, making it accessible to anyone.

Here we opened it, and modified the document from VM2(WIN2) desktop.

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/53cbb805-ac7e-4335-867e-9467bcae66ed)


Here we can see it from VM1. We will download and view it to ensure it was modified.
![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/ff5b41db-bc06-4899-9c64-1f8a472eb0fb)

![image](https://github.com/itnatepena/azure-vm-network-project/assets/147539410/91399917-ba35-4d15-bcab-09a47aaf8941)


## What We Learned

In this project, we showed how to:

- Create Azure Virtual Machines.
- Configure ICMPv4 rules in Network Security Groups.
- Test ICMPv4 connectivity between VMs.
- Install and use Wireshark for network traffic capture.
- Share documents between VMs.
- Modify and reshare documents.
- Transfer files to a local desktop.

This project provides a practical exercise in Azure VM connectivity, network traffic analysis, and file sharing within a virtual network environment.
