# Azure VM Connectivity and File Sharing Lab

## Introduction

This project aims to provide a comprehensive demonstration of the process involving the creation of two Azure virtual machines (VMs), the testing of ICMPv4 connectivity between these VMs, capturing network traffic with Wireshark, sharing documents between VMs, modifying and resharing documents, and ultimately transferring a file to a local desktop.

## Prerequisites

- Microsoft Azure
- Azure Data Studio

## Step 1: Create Azure Virtual Machines

1. Log in to your Azure portal.
2. Create two Windows 10 Azure VMs (VM1 and VM2) within the same Azure Virtual Network and subnet.

## Step 2: Allow ICMPv4 Addresses

1. Configure Network Security Group (NSG) rules to allow ICMP (ping) traffic between VM1 and VM2.

## Step 3: Test ICMPv4 Connectivity

1. Connect to VM1 and use the Command Prompt to ping VM2. Ensure successful ICMPv4 connectivity.
2. Similarly, connect to VM2 and ping VM1.

## Step 4: Install Wireshark on VM1

1. Download and install Wireshark on VM1 to capture network traffic.

## Step 5: Test Connectivity and View in Wireshark

1. Start a packet capture in Wireshark on VM1.
2. On VM2, ping VM1 and observe the captured ICMPv4 packets in Wireshark.

## Step 6: Create a Shareable Document

1. On VM1 (also known as Win1), create a document that you want to share between VMs.

## Step 7: Share the Document

1. Share the document on Win1 and set it as shareable with specific user permissions. Apply the changes.

## Step 8: Restart to Apply Settings

1. Restart VM1 to ensure that the document sharing settings take effect.

## Step 9: Access VM1 (Win1) from VM2 (Win2)

1. On Win2 (VM2), navigate to Win1's shared resources using the path \\Win1\SharedFolderName.

## Step 10: Transfer the Document to Local Desktop

1. Copy the shared document from Win1 to your local desktop (the desktop of the machine you are using to access VMs).

## Step 11: Modify and Reshare the Document

1. Modify the document locally and reshare it from your local desktop, making it accessible to anyone.

## Step 12: Document and Finalize

1. Document the observations, steps, and findings in your project documentation.
2. Share the project documentation and any insights gained with others on your Azure Virtual Network.

## What We Learned

In this project, we learned how to:

- Create Azure Virtual Machines.
- Configure ICMPv4 rules in Network Security Groups.
- Test ICMPv4 connectivity between VMs.
- Install and use Wireshark for network traffic capture.
- Share documents between VMs.
- Modify and reshare documents.
- Transfer files to a local desktop.

This project provides a practical exercise in Azure VM connectivity, network traffic analysis, and file sharing within a virtual network environment.
