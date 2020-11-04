# Requirements

#### [prev](./concepts.md) | [home](./welcome.md)  | [next](./deployment-s20.md)

The WVD Docs article lists all requirements on the 'Overview' page located [here](https://docs.microsoft.com/en-us/azure/virtual-desktop/overview). 

> Note that there are two WVD documentations, one for the [Current release](https://docs.microsoft.com/en-us/azure/virtual-desktop/) aka Spring 2020 and [Classic Release](https://docs.microsoft.com/en-us/azure/virtual-desktop/virtual-desktop-fall-2019/tenant-setup-azure-active-directory) aka Fall 2019 release.

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


## Security
- An important point.

## 'Split' or 'Single' deployment options

Decide to deploy all components to a single Azure AD Tenant or to split the WVD integration with a separate (non-production) Azure AD Tenant.

Split deployment: The majority of resources can be deployed to a Corp Azure AD Tenant. Specifc directory integration resources will be split and deployed separately. The cost of the split resources will be minimal, and a trial subscription can be used. 

Single deployment: this option requires that you manually setup your Azure AD and on-premises Domain Services integration. 

> At least one subscription per tenant is required with tenant trust enable. 
