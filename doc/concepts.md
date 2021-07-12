# Concepts

#### [prev](./what.md) | [home](./welcome.md)  | [next](./requirements.md)

## Structure
* Host pools
* App Groups
* Workspaces
* End Users


## Host pools
A host pool is a collection of Azure virtual machines that register to Azure Virtual Desktop as session hosts when an agent is deployed. 
All session host virtual machines in a host pool should be sourced from the same image for a consistent user experience.

A host pool can be one of two types:

* Personal, where each session host is assigned to individual users.
* Pooled, where session hosts can accept connections from any user authorized to an app group within the host pool.

You can set additional properties on the host pool to change its load-balancing behavior, how many sessions each session host can take, and what the user can do to session hosts in the host pool while signed in to their Windows Virtual Desktop sessions. You control the resources published to users through app groups.
A key consideration is that you need a host pool for users to access desktops and applications. Currently the service is limited in that you can either access desktops OR applications from within a host pool, not both. However users CAN be assigned to multiple app groups.  

## Application Groups
Application groups are logical grouping of applications and desktops for a given Host Pool. They are two types:

* Desktop, where users access the full desktop
* RemoteApp, where users access the RemoteApps you individually select and publish to the app group

By default, a desktop app group named "HOSTPOOL-DAG" (Where HOSTPOOL is the actual pool name) (Friendly named "Desktop Application Group" which can be changed) is automatically created whenever you create a host pool. You can remove this app group at any time. However, you can't create another desktop app group in the host pool while a desktop app group exists. To publish RemoteApps, you must create a RemoteApp app group. You can create multiple RemoteApp app groups to accommodate different worker scenarios. Different RemoteApp app groups can also contain overlapping RemoteApps.

To publish resources to users, you must assign them to app groups. When assigning users to app groups, consider the following things (as shared above):

* A user can be assigned to both a desktop app group and a RemoteApp app group in the same host pool. However, users can only launch one type of app group per session. Users can't launch both types of app groups at the same time in a single session.
* A user can be assigned to multiple app groups within the same host pool, and their feed will be an accumulation of both app groups.

## Workspaces
A workspace is a logical grouping of application groups. 
Each application group must be associated with a workspace for users to see the remote apps and desktops published to them.

## End users

End users need to be the users from your Active Directory which are then sycned to your Azure Active Directory (AAD) tenant.(AVD Subscriptions will need to be associated with this tenant). 

This is because the virtual machines (or session hosts) are domain joined to your AD therefore the users need to exist there for them to be able to access the hosts and applications.  


## Visual Representation
In order to understand where all these pieces sit, please refer to the below high level diagram
![Concept Diagram](/png/wvd-concepts-diag.png)

End user representation from AVD Remote Desktop Client

![End user view](/png/wvd-solution-end-user-view.png)

## Helpful links
[Azure Virtual Desktop Environment](https://docs.microsoft.com/en-us/azure/virtual-desktop/environment-setup)

[Azure Academy - Building WVD Environment](https://aka.ms/AzureAcademy-WVD)

These concepts will help you understand the hierarchy you need to establish in order to deploy AVD

