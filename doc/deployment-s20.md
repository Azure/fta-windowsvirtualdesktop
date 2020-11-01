# Deployment

#### [prev](./deployment-f19.md) | [home](./welcome.md)  | [next](./management.md)

## Before you deploy

- Sizing is very important element for successful deployment of WVD.
- Users can run different types of workloads on VMs managed by Windows Virtual Desktop. 
- Plan to scale your deployment depending on the expected need of [each type of user](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remote-desktop-workloads).
- Choose right VM size (Cores/Memory/Disk/Graphics) depending on the purpose.
- For [Multi-session (Pooled), this table](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context#multi-session-recommendations) lists the maximum suggested number of users per virtual central processing unit (vCPU) and the minimum VM configuration for each workload.
- VM sizing for [single-session VMs](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context#single-session-recommendations) will likely align with physical device guidelines.
 
 - Profile Storage Sizing. (Mainly IOPS).
    - Requirements can vary widely depending on the user, applications, and activity on each profile.
    - General requirements, Steady state IOPS	10, Sign-in/sign-out IOPS	50 per user
    - [Refer details here](https://docs.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#performance-requirements)
 
 
 

## WVD Service

Follow the tutorial
- Create a host pool with the Azure portal - step #1 in the tutorial
- Manage app groups with the Azure portal - step #2 in the tutorial
- Create a host pool to validate service updates - step #3 in the tutorial
- Set up service alerts - step #4 in the tutorial

[WVD Tutorial](https://docs.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)


## FSLogix
- [What is FSLogix?](https://docs.microsoft.com/en-us/fslogix/overview)
- [Storage options for FSLogix profile containers in Windows Virtual Desktop](https://docs.microsoft.com/en-us/azure/virtual-desktop/fslogix-containers-azure-files)
- [Setup Azure Files as FSLogix profile share with Active Directory integration](https://docs.microsoft.com/en-us/azure/virtual-desktop/create-file-share)
    
