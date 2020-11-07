# Management

#### [prev](./deployment-s20.md) | [home](./welcome.md)  | [next](./resources.md)

## Host VM Image.
- Custom Image. Use standard process of generalizing (sysprep).
- Would vary depending the requirements but typical steps are to install standard softwares, customize for "Multi-user" environment etc.
- [Create a VM from image](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/capture-image-resource)
- [Customize image for Office applications](https://docs.microsoft.com/en-us/azure/virtual-desktop/install-office-on-wvd-master-image)

## Ongoing Management/updates.
-  Build new image, set existing to drain mode, replace VMs from new image.
-  This works best for Pooled Hosts with FSLogix profiles. (Profiles are decoupled)
-  With MSIX App Attach (In Public Preview), applications can also be decoupled from OS. 
-  Microsoft Endpoint Configuration Manager branch level 1906 and above for applying [updates](https://docs.microsoft.com/en-us/azure/virtual-desktop/configure-automatic-updates) Multi-session Windows 10.
-  Other approaches like Windows update for business may work with some caveats. 

## Device Management. 
-  Windows 10 Enterprise multi-session supports to be hybrid Azure AD-joined.
-  You can manage Active Directory or hybrid Azure Active Directory joined **Windows 10 Enterprise** Virtual Desktop VMs with Microsoft Endpoint Manager (Intune)
-  MEM support for multi-session is on the roadmap. 

## Automation 
-  Start/Stop VMs to save cost. Official solution is available which is based on [Azure Automation/Logic App](https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-scaling-script).
-  [ARM Templates](https://github.com/Azure/RDS-Templates/tree/master/ARM-wvd-templates) to create new host pools/add VMs to existing.
-  Build Image using [Azure DevOps and Azure Image Builder](https://techcommunity.microsoft.com/t5/windows-virtual-desktop/building-a-windows-10-enterprise-multi-session-master-image-with/m-p/1503913)

## Monitor WVD Environment
-  Use [Azure Monitor](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/proactively-monitor-arm-based-windows-virtual-desktop-with-azure/ba-p/1508735)

## Security
-  Gateway/Broker etc is Microsoft Managed. Reverse Connect so no inbound public access to Host VMs
-  MFA, Conditional Access
-  RemoteApp instead of full desktops
-  Endpoint protection. 
-  Disconnect inactive sessions 
-  Screen lock.
-  Device redirection restrictions 
-  Endoint Security. Intune/MDM.
-  WVD Infrastrcture Network Security, NSG, NVA/Firewall 

## Feature update roadmap.
-  Latency improvements in varios regions (Gateways)
-  Direct connectivity between client and session hosts over managed networks.
-  Metadata in EU region.
-  Prevent screen capturing.
-  Start host VM on connect.
-  MEM (Intune) support for Windows 10 multi-session.
-  MSIX App attach.
