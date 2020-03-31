# WVD Requirements

The WVD Docs article lists all requirements on the 'Overview' page located [here](https://docs.microsoft.com/en-us/azure/virtual-desktop/overview). 

## Supporting infrastructure

- Domain Services: 
WVD host pool VMs must be domain joined. This requires either an on-premises forest or the use of Azure AD Domain Services.
- File Services: To enable persistant profile for users a file service is needed which supports domain integration. Azure Files can be used for this.
- Azure AD with integration to Domain Services.
- Other required infrastructure is listed on the WVD overview page.
- Azure subscription

## 'Split' or 'Single' deployment options

Decide to deploy all components to a single Azure AD Tenant or to split the WVD integration with a separate (non-production) Azure AD Tenant.

Split deployment: The majority of resources can be deployed to a Corp Azure AD Tenant. Specifc directory integration resources will be split and deployed separately. The cost of the split resources will be minimal, and a trial subscription can be used. 

Single deployment: this option requires that you manually setup your Azure AD and on-premises Domain Services integration. 

> A subscription per tenant is required with tenant trust enable. 
