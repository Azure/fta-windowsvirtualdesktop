# Deployment

#### [prev](./deployment-f19.md) | [home](./welcome.md)  | [next](./management.md)

## Before you Deploy.

- Sizing is very important element for successful deployment of AVD.
- Users can run different types of workloads on VMs managed by Azure Virtual Desktop. 
- Plan to scale your deployment depending on the expected need of [each type of user](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remote-desktop-workloads).
- Choose right VM size (Cores/Memory/Disk/Graphics) depending on the purpose.
- For [Multi-session (Pooled), this table](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context#multi-session-recommendations) lists the maximum suggested number of users per virtual central processing unit (vCPU) and the minimum VM configuration for each workload.
- VM sizing for [single-session VMs](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/virtual-machine-recs?context=/azure/virtual-desktop/context/context#single-session-recommendations) will likely align with physical device guidelines.
 
- FSLogix Profile Storage Sizing. (Mainly IOPS).
    - Requirements can vary widely depending on the user, applications, and activity on each profile.
    - General requirements, Steady state IOPS	10, Sign-in/sign-out IOPS	50 per user
    - [Refer details here](https://docs.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#performance-requirements)
  - End user network bandwidth [requirements](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/network-guidance). 
    Recommended bandwidth based on workloads (user personas)
      - Light	1.5 Mbps
      - Medium	3 Mbps
      - Heavy	5 Mbps
      - Power	15 Mbps
- Operting System Image. Marketplace or custom.

- User/client connectivity.
  - AVD Client apps, HTML5 compatible browsers.
  - Apps from respective stores. 
  - Windows comes wiht two apps, a store app and regular Windows client.
  - Features/capabilities differs. 
  
## Azure Landing Zone
-  It is still a IaaS pattern of cloud, so good planning around Azure governance, security, management is very important.
-  Attend our FastTrack for Azure Governance call to learn more.
-  Refer Azure Cloud Adoption Framework for guidelines. (Ready phase).
 
## Lets Depoly.

Follow the tutorial
[AVD Tutorial](https://docs.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)


## FSLogix
- [What is FSLogix?](https://docs.microsoft.com/en-us/fslogix/overview)
- [Storage options for FSLogix profile containers in Azure Virtual Desktop](https://docs.microsoft.com/en-us/azure/virtual-desktop/fslogix-containers-azure-files)
- [Setup Azure Files as FSLogix profile share with Active Directory integration](https://docs.microsoft.com/en-us/azure/virtual-desktop/create-file-share)
    
