# Management

#### [prev](./deployment-s20.md) | [home](./welcome.md)  | [next](./resources.md)

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

https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/rdp-files?context=/azure/virtual-desktop/context/context

