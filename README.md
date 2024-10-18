# VM Setup and OS Installation Guide

This guide will walk you through the process of creating a Virtual Machine (VM) in VirtualBox, installing an operating system (OS) on it, and configuring network settings for internet access. 

Before you start, ensure you have gone through the prerequisites mentioned in the (devops-guide/prequisites).

---

## 1. Virtual Machine Creation in VirtualBox

### Steps to Create a New VM:

1. **Open the VM VirtualBox Manager**.
2. Click on **New** to create a new VM.
3. Follow the below steps to configure your VM:
   - **Name** the VM.
   - Choose the **folder** where you want to host the VM.
   - Do **not** select an ISO file yet (we'll do this later).
   - Select the **OS family** you want to install:
     - Choose **Linux**.
     - For the guest OS, select **CentOS (64-bit)**.
   - Set the **RAM** (2048 MB recommended) and **CPU** (2 CPUs recommended).
   - Create a **virtual disk** with a size of 20 GB (recommended).
4. Verify the configuration settings and click on **Finish**.

> *Repeat the same steps to create a RedHat VM if needed.*

---

## 2. Installing OS on the VM

### Steps to Install OS:

1. Download the **CentOS 9 ISO file** from the following URL:  
   [CentOS Stream 9 ISO](https://mirror.stream.centos.org/9-stream/BaseOS/x86_64/iso/CentOS-Stream-9-20241016.0-x86_64-boot.iso)
   
2. Open **VirtualBox**, select the VM you want to install the OS on (e.g., CentOS VM), and go to its **Settings**.

3. Follow these steps:
   - Go to **Storage** settings.
   - Under **Controller: IDE**, click on the disk icon.
   - In the **Attributes** section, click on the disk icon, then locate and select the **ISO file** you downloaded earlier.
   - Check the option for **Live CD/DVD**.

---

## 3. Configuring Network Settings

1. In the **Settings** tab, go to **Network** settings.
2. Under the **Adapter 2** tab:
   - Enable the network adapter for the VM (this will allow internet access).
   - Select **Bridged Adapter** from the dropdown.
   - Ensure you select an option that connects to your WiFi (since most machines connect to the internet via WiFi).

---

## 4. Installation Setup

1. Start the VM and select your **preferred language**.
2. From the installation summary window:
   - Click on **Installation Destination**, then click on the virtual hard disk of the VM.
   - Repeat this process twice to select the partition scheme as **Automatic**.
   
3. Go back to the installation summary window, and:
   - Select **Network & Host Name**.
   - Set the **hostname**.
   - Verify the **Bridged Adapter IP** and ensure your WiFi's IP matches the default.
   
4. Set the **Root Password**.

5. Click on **Begin Installation**.

---

## 5. Post-Installation Steps

1. **Power off the VM**.
2. Before starting the VM again, remove the disk from the virtual drive:
   - Go back to **Settings** > **Storage**.
   - From the **Controller: IDE**, click on the disk icon, and remove the attached ISO file (this prevents the VM from booting into the ISO again).
   
3. Power-on the VM.

4. You can now **SSH into the VM** via a terminal like Git Bash.

---

You're now ready to use your VM with the installed OS!

