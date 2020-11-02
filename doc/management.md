# Management

#### [prev](./deployment-s20.md) | [home](./welcome.md)  | [next](./resources.md)

## Host VM Image.
- Custom Image. Use standard process of generalizing (sysprep).
- Would vary depending the requiremente but typical steps are to install standard softwares, customize for "Multi-session" environment etc.
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
-  Start/Stop VMs to save cost. Official solution is available which is based on [Azure Automation/Logic App](https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-scaling-script)

## Management related links Fall 2019
- https://github.com/Azure/RDS-Templates/tree/master/wvd-templates/wvd-management-ux/deploy
- https://rdweb.wvd.microsoft.com/webclient/index.html
- https://rdbroker.wvd.microsoft.com

## Management related links Spring 2020
- https://github.com/Azure/RDS-Templates/tree/master/wvd-templates/wvd-management-ux/deploy
- https://rdweb.wvd.microsoft.com/arm/webclient/index.html

## Updates coming to the service Public Preview
- Expected public preview date: out now!
- Expected General Availability date: details coming soon.
- Keep an eye here https://azure.microsoft.com/en-us/updates/
- Integration with ARM.
- Geo distribution to host WVD data.

## What happens to my previous deployments
- You will be expected to migrate to the latest release (ARM integrated release)
- There will be a grace period (this length has not been decided).
- Your existing host pools won't change.

## Management Portal
- Management Portal is deployed from [GitHub](https://github.com/Azure/RDS-Templates/tree/master/wvd-templates/wvd-management-ux/deploy) 
- Deploy from here using the AD Tenant used to register your domain against 
- Deploy this early.

## Monitoring Tenant, VMs, Sessions
- Monitoring of the host pools is no different to monitoring Azure Virtual Machines.
- Use Azure Monitor with Log Analytics.
- There are free 3rd party solution to help create dashboards.

## Image Maintenance
- Patching host pool VMs.
- Installing / updating applications.
- Use [Azure Image Creator](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/capture-image-resource)

## Automate scale and host pool VM deployments
- [Scale session hosts using Azure Automation](https://docs.microsoft.com/en-us/azure/virtual-desktop/virtual-desktop-fall-2019/set-up-scaling-script)

## Troubleshooting
- Host pools are just VMs.
- Interact with the WVD service using PowerShell.

## Client Options
- Mapped drives and printers.
- Security.
- Remote app Start menu integration.
- [Supported Remote Desktop RDP file settings](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/rdp-files?context=/azure/virtual-desktop/context/context)

