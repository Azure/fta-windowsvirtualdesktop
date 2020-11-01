# What is Windows Virtual Desktop (WVD)?

#### [prev](./welcome.md) | [home](./welcome.md)  | [next](./concepts.md)

App virtualization and Remote Desktop as a Service
[https://docs.microsoft.com/en-us/azure/virtual-desktop/overview](https://docs.microsoft.com/en-us/azure/virtual-desktop/overview)

In the past if you wanted deploy Remote Desktop Services (RDS) it was complex with several components which needed to be deployed and managed by the customer
see [reference architecture](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/desktop-hosting-logical-architecture)

## Possible Scenarios
* Legacy Line of Business application that have no native way to share across platforms and devices
* Resource optimization e.g applications that are resource intensive
* Enabling user mobility especially in short time-frames, tactical response

## Other Enablers for Remote Workers
* [Remote Desktop](https://docs.microsoft.com/en-us/windows/win32/termserv/remote-desktop-protocol)
* [AAD Application Proxy](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/application-proxy)
* [App Service with AAD Authentication](https://docs.microsoft.com/en-us/azure/app-service/overview-authentication-authorization)
* [Mobile Device Management (MDM)](https://docs.microsoft.com/en-us/mem/)
* [Conditional Access](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)
* [Windows 10 VPN](https://docs.microsoft.com/en-us/windows/security/identity-protection/vpn/vpn-guide)
* Partner products such as Citrix, VMWare

## What you can with WVD
* Set up a multi-session Windows 10 deployment that delivers a full Windows 10 with scalability
* Virtualize Microsoft 365 Apps for enterprise and optimize it to run in multi-user virtual scenarios
* Provide Windows 7 virtual desktops with free Extended Security Updates
* Bring your existing Remote Desktop Services (RDS) and Windows Server desktops and apps to any computer
* Virtualize both desktops and apps
* Manage Windows 10, Windows Server, and Windows 7 desktops and apps with a unified management experience

## Solution Overview
3 Main components
![Concept Diagram](/png/wvd-solution-overview.png)
