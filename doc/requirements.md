# Requirements

#### [prev](./concepts.md) | [home](./welcome.md)  | [next](./deployment-s20.md)

The WVD Docs article lists all requirements on the 'Overview' page located [here](https://docs.microsoft.com/en-us/azure/virtual-desktop/overview). 

## Supporting infrastructure
- Azure subscription.
- Azure AD tenant.
- Domain Services: 
Host pool VMs must be domain joined to either an on-premises domain or to Azure AD Domain Services (AADDS).
- Users synced to Azure AD: this means deploying Azure AD Connect if using on-premises domain services.
- File Services: To enable persistent profile for users a file service is needed which supports domain integration. Depending on requirements (read sizing), SOFS on Windows VM based File shares, Azure Files, Azure NetApp Files can be used for this.
- Azure networking.
- Network connectivity to production systems.

## End to end connectivity
- Routing.
- Firewall rules.

## Access
- To create host pools and other objects, Contributor role on the subscription or resource group.
- To publish app groups to users or user groups,User Access Admin role.
- Custom roles are possible/supported. [Sample here](https://github.com/DeanCefola/Azure-WVD/tree/master/WVD%20Permissions)


