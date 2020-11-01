# Concepts

#### [prev](./what.md) | [home](./welcome.md)  | [next](./requirements.md)

## Helpful links
[Windows Virtual Desktop Environment](https://docs.microsoft.com/en-us/azure/virtual-desktop/environment-setup)

[Azure Academy - Building WVD Environment](https://aka.ms/AzureAcademy-WVD)

These concepts will help you understand the hierarchy you need to establish in order to deploy WVD

## Structure
* Host pools
* App Groups
* Workspaces
* End Users


## Host pools
A host pool is a collection of Azure virtual machines that register to Windows Virtual Desktop as session hosts when you run the Windows Virtual Desktop agent. All session host virtual machines in a host pool should be sourced from the same image for a consistent user experience.

A host pool can be one of two types:

* Personal, where each session host is assigned to individual users.
* Pooled, where session hosts can accept connections from any user authorized to an app group within the host pool.

You can set additional properties on the host pool to change its load-balancing behavior, how many sessions each session host can take, and what the user can do to session hosts in the host pool while signed in to their Windows Virtual Desktop sessions. You control the resources published to users through app groups.
A key consideration is that you need a host pool for users to access desktops and applications. Currently the service is limited in that you can either access desktops OR applications from within a host pool, not both. However users CAN be assigned to multiple app groups.  

## App Groups
An app group is a logical grouping of applications installed on session hosts in the host pool. An app group can be one of two types:

* RemoteApp, where users access the RemoteApps you individually select and publish to the app group
* Desktop, where users access the full desktop

By default, a desktop app group named "HOSTPOOL-DAG" (Where HOSTPOOL is the actual pool name) (Friendly named "Desktop Application Group" which can be changed) is automatically created whenever you create a host pool. You can remove this app group at any time. However, you can't create another desktop app group in the host pool while a desktop app group exists. To publish RemoteApps, you must create a RemoteApp app group. You can create multiple RemoteApp app groups to accommodate different worker scenarios. Different RemoteApp app groups can also contain overlapping RemoteApps.

To publish resources to users, you must assign them to app groups. When assigning users to app groups, consider the following things (as shared above):

* A user can be assigned to both a desktop app group and a RemoteApp app group in the same host pool. However, users can only launch one type of app group per session. Users can't launch both types of app groups at the same time in a single session.
* A user can be assigned to multiple app groups within the same host pool, and their feed will be an accumulation of both app groups.

## Workspaces
The Windows Virtual Desktop tenant is the primary interface for managing your Windows Virtual Desktop environment. Each Windows Virtual Desktop tenant must be associated with the Azure Active Directory containing the users who will sign in to the environment. From the Windows Virtual Desktop tenant, you can begin creating host pools to run your users' workloads.
The WVD Tenant was effectively the top level of WVD administration, this directly translates to a WVD Workspace in the ARM model. To publish applications or desktops to users, they need to be assigned to an “App Group” which in turn needs to be registered to a Workspace.

## End users
End users need to be the users from your Active Directory (AD) NOT your Azure Active Directory (AAD). This is because the virtual machines (or session hosts) are domain joined to your AD therefore the users need to exist there for them to be able to access the hosts and applications.  


## Visual Representation
In order to understand where all these pieces sit, please refer to the below high level diagram
![Concept Diagram](/png/wvd-concepts-diag.png)
