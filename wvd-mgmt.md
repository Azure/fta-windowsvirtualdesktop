# Management

## Management related links
- https://github.com/Azure/RDS-Templates/tree/master/wvd-templates/wvd-management-ux/deploy
- https://rdweb.wvd.microsoft.com/webclient/index.html
- https://rdbroker.wvd.microsoft.com

## Updates coming to the service Public Preview
- Expected public preview date: details coming soon.
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

## Troubleshooting
- Host pools are just VMs.
- Interact with the WVD service using PowerShell.

