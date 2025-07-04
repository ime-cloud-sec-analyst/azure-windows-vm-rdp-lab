# azure-windows-vm-rdp-lab
Azure lab project to deploy a Windows Server VM, configure NSG rules, enable RDP, and connect via Remote Desktop from a local Windows 10 machine.
# 🚀 Azure Windows VM RDP Lab

This project documents the hands-on lab steps for deploying and remotely accessing a Windows Server virtual machine using Microsoft Azure. The goal is to demonstrate creating, configuring, and connecting to a Windows VM from a local Windows 10 machine using RDP.

---

## 🧪 Lab Objective

- Deploy a Windows Server 2022 Datacenter VM in Azure
- Configure Network Security Group (NSG) rules for RDP (port 3389)
- Connect to the VM via Remote Desktop Protocol (RDP)
- Troubleshoot SSH and RDP connection issues
- Test and document possible misconfigurations

---

## 🛠️ Tools & Environment

- **Azure Portal**
- **Windows 10 PC**
- **Remote Desktop Connection**
- **Azure CLI / Cloud Shell**
- **GitHub** (to document and store evidence)

---

## 📝 Step-by-Step Summary

1. **Create Resource Group**:  
   Created `myResourceGroup` in `UK South`.

2. **Create Virtual Network & Subnet**:  
   Used default settings, name: `my-VM-vnet`.

3. **Create Windows VM**:  
   - Name: `my-VM`  
   - Image: Windows Server 2022 Datacenter  
   - Size: Standard B1s  
   - Username: `azureuser`

4. **Create NSG & Rules**:  
   Added Inbound rules to allow:
   - **SSH** (port 22)  
   - **RDP** (port 3389)

5. **Connect via SSH (Failed)**:  
   Attempted `ssh azureuser@<public-ip>` but received timeout error due to OS mismatch (Windows OS instead of Linux).

6. **Connect via RDP (Succeeded)**:  
   - Used public IP in Windows RDP  
   - Logged in successfully to `azureuser`  
   - Screenshot shows successful login screen

7. **Troubleshooting**:  
   - Identified the root cause of SSH failure  
   - Enabled RDP via NSG  
   - Demonstrated proper OS-based access method

---

## 📸 Screenshots

All screenshots from setup and troubleshooting have been uploaded in the repository for step-by-step reference.

---

## 🧠 Lessons Learned

- Always match connection method to OS (SSH for Linux, RDP for Windows).
- Ensure NSG rules are correctly configured before connecting.
- Confirm that VM status is **Running** and **Remote Access** is enabled.
- Use Azure portal diagnostics to investigate failed access attempts.

---

## 📂 Folder Structure

```bash
/azure-windows-vm-rdp-lab
│
├── screenshots/
│   ├── create-vm.png
│   ├── ssh-failure.png
│   ├── nsg-rdp-rule.png
│   ├── successful-rdp-login.png
│   └── ...
│
└── README.md

Created by Dr. Ime Ben as part of Microsoft Azure Hands-on Cloud Lab.
