## Product Overview
InfraManage Enterprise is a one-to-many systems management and monitoring web application delivered as a virtual appliance.
It provides a centralized view of servers, chassis, storage systems, network switches, and supported third-party devices across the enterprise network.
It is designed for the next generation IT professionals with a focus on simplicity, 
automation, and unification of data center management.

## Key Features

With InfraManage Enterprise, users can:

- Discover devices across the data center environment.
- View detailed hardware inventory and monitor device health.
- View, manage, and configure alert policies for events received by the appliance.
- Monitor firmware and driver versions across managed devices.
- Perform firmware and driver updates using predefined firmware baselines.
- Execute remote management tasks, such as power control, on devices.

- ## Deployment Overview

InfraManage Enterprise is delivered as a virtual appliance that is deployed on a supported hypervisor. After the initial network provisioning using the Text User Interface (TUI), the appliance can be configured and managed through the web-based application client.

To view or update the current InfraManage Enterprise version, see *Updating the Console.

---

## Topics Covered
- Host system requirements
- Deployment best practices
- Deployment prerequisites
- Deploying in VMware vSphere
- Deploying in Microsoft Hyper-V
- Deploying in KVM
- Programmatic deployment
- System configuration using the TUI

---

## Host System Requirements

Ensure that the minimum system requirements are met before deploying InfraManage Enterprise.

> **Note:**  
> For the most up-to-date system requirements, refer to the latest version of the InfraManage Enterprise Support Matrix.

---

### Minimum Host System Requirements

| System Component | Minimum Requirements |
|------------------|----------------------|
| **Hypervisors** | VMware vSphere supported on ESXi 6.7 or later.<br><br>Secure Boot requires firmware boot option as Extensible Firmware Interface (EFI) and is supported only on ESXi 6.7 or later.<br><br>Ensure that the ESXi host to be deployed is disconnected from vCenter.<br><br>Microsoft Hyper-V Generation 2 virtual machines supported on Windows Server 2019 or later.<br><br>KVM supported on Red Hat Enterprise Linux 6.5 or later.<br><br>QEMU deployments supported on machine type q35 or later. |
| **Network** | Available virtual NIC with access to the management networks of all managed devices. |
| **Web Browsers** | Internet Explorer (64-bit) 11 or later.<br>Mozilla Firefox 52 or later.<br>Google Chrome 58 or later.<br>Microsoft Edge version 41.16299 or later. |

## Maximum Recommended Hardware Configuration

Starting with InfraManage Enterprise version 4.1, the appliance is shipped with the maximum recommended hardware configuration to ensure a smooth deployment and installation of the appliance and its plug-ins.

If your environment does not require the maximum hardware configuration, see *Managing Memory and CPU Requirements Based on Deployment Size* to determine the appropriate hardware resources for your specific needs.

The following table lists the default recommended hardware configuration for installing InfraManage Enterprise and all supported plug-ins.

### Appliance Default Hardware Configuration

| Hardware Configuration | RAM  | Processor Cores | Hard Drive Space |
|------------------------|------|-----------------|------------------|
| Default (Maximum)      | 64 GB| 8               | 830 GB           |


## Deploy in VMware vSphere

This section describes how to deploy InfraManage Enterprise in a VMware vSphere environment using an Open Virtualization Format (OVF) template.

---

## Prerequisites

Before you begin, ensure that the following requirements are met:

- VMware vSphere ESXi version 6.7 or later is available.
- When deploying on OVF specification–based hypervisors, thick provisioning is recommended.
- Use the supplied OVF template, which is configured with the minimum hardware requirements required to run the InfraManage Enterprise appliance.
- Ensure that the ESXi host selected for deployment is disconnected from vCenter.

> **Note:**  
> If a secondary network adapter is added before powering on the appliance for the first time, IPv4 and IPv6 are disabled on that adapter by default.  
> After logging in to the Text User Interface (TUI), accepting the EULA, and changing the administrator password, the adapter appears as **Disabled** and must be configured manually by the user.

---

## Procedure

1. Download the `inframange_enterprise_ovf_format.zip` file from the support site and extract the contents to a location accessible by the VMware vSphere Client.  
   It is recommended to use a local drive or CD/DVD, as installing from a network location may take up to 30 minutes.

2. In the **Virtual Machines** screen, click **Create/Register VM**.  
   The **New Virtual Machine** wizard opens.

3. On the **Select creation type** screen, select **Deploy a virtual machine from an OVF or OVA file**, and then click **Next**.

4. On the **Select OVF and VMDK files** screen:
   - Enter a name for the virtual machine.
   - Drag and drop the extracted OVF and VMDK files, or click the screen to upload all required files.
   - Click **Next**.

5. On the **Select storage** screen, verify that the selected datastore has sufficient free space to meet the InfraManage Enterprise hardware requirements.  
   Click **Next**.

6. On the **Deployment options** screen, set **Disk provisioning** to **Thick** to pre-allocate physical storage space for the virtual machine.  
   Click **Next**.

7. On the **Ready to complete** screen, review the configuration settings and click **Finish**.

A completion status window displays, allowing you to monitor the deployment progress. After the deployment completes, the virtual machine powers on automatically.

---

## Result

InfraManage Enterprise is successfully deployed in the VMware vSphere environment.



