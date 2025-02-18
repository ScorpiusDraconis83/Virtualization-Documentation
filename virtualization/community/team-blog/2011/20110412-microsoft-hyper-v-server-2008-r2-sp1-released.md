---
title:      "MICROSOFT HYPER-V SERVER 2008 R2 SP1 RELEASED!"
author: sethmanheim
ms.author: mabrigg
description: Microsoft Hyper-V Server 2008 R2 SP1 released!
ms.date: 04/12/2011
date:       2011-04-12 15:38:00
categories: hyper-v
---
# Microsoft Hyper-V Server 2008 R2 SP1 released!

Virtualization Nation,

The good news just keeps coming and we’re pleased to keep the momentum rolling with the latest release of our rock stable, feature rich, standalone Microsoft Hyper-V Server 2008 R2 with Service Pack 1! For those who need a refresher on Microsoft Hyper-V Server 2008 R2, it includes key features based on customer feedback such as:

  * Live Migration

  * High Availability with Failover Clustering

  * Cluster Shared Volumes

  * 10 Gb/E Ready

  * Processor Compatibility Mode

  * Enhanced Scalability

  * …and much more.




For more info on Microsoft Hyper-V Server 2008 R2, read: [here](https://techcommunity.microsoft.com/t5/virtualization/microsoft-hyper-v-server-2008-r2-rtm-more/ba-p/381635). Service Pack 1 for Hyper-V Server 2008 R2 includes all the rollup fixes released since Microsoft Hyper-V Server 2008 R2 and adds two new features that greatly enhance VDI scenarios:

  * Dynamic Memory

  * RemoteFX


After installing the update, both Dynamic Memory and [RemoteFX](https://technet.microsoft.com/library/ff817578\(WS.10\).aspx) will be available to Hyper-V Server. These new features can be managed in a number of ways:

  * Using the updated R2 SP1 Hyper-V Manager user interface on a full version of Windows Server 2008 R2 SP1

  * [Using the updated Remote Server Administration Tools (RSAT) for Windows 7 & Windows 7 SP1](https://www.microsoft.com/downloads/en/details.aspx?FamilyID=7d2f6ad7-656b-4313-a005-4e344e43997d)

  * [System Center Virtual Machine Manager 2008 R2 SP1](https://www.microsoft.com/systemcenter/en/us/virtual-machine-manager/vmm-whats-new-r2.aspx)

  * [System Center Virtual Machine Manager 2012 Beta](https://www.microsoft.com/systemcenter/en/us/virtual-machine-manager/vm-vnext-beta.aspx)




Dynamic memory is an enhancement to Hyper-V R2 which pools all the memory available on a physical host and dynamically distributes it to virtual machines running on that host as necessary. That means based on changes in workload, virtual machines will be able to receive new memory allocations without a service interruption through Dynamic Memory Balancing. In short, Dynamic Memory is exactly what it’s named. If you’d like to know more, I've included numerous links on Dynamic Memory below.

**Configuring RemoteFX with Microsoft Hyper-V Server 2008 R2 SP1**

Although using Dynamic Memory does not need any additional server side configuration beyond installing the R2 SP1 update, enabling RemoteFX does require some additional configuration on the host.  The exact steps for enabling the RemoteFX are detailed below:

1)      Verify the host machine meets the [minimum hardware requirements](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff817602(v=ws.10)) for RemoteFX. 

2)      Verify the host has the latest 3D graphics card drivers installed before enabling RemoteFX.

3)      Enable the RemoteFX feature using the following command line:

**Dism.exe   /online /enable-feature /featurename:VmHostAgent**

4)      From a remote machine running the full version of Windows Server 2008 R2 SP1 or a client OS running the latest version of RSAT, connect to the Hyper-V Server machines, create a Windows 7 R2 SP1 virtual machine and under “Add Hardware”, select “RemoteFX 3D Video Adapter”.  Select “Add”.



 If the “RemoteFX 3D Video Adapter” option is greyed out, it is usually because RemoteFX is not enabled or the 3D video card drivers have not been installed on the host yet. _Before attaching the RemoteFX adapter_ , make sure to set user access permissions, note the computer name and enable Remote Desktop within the VM first. When the RemoteFX 3D video adapter is attached to the VM, you will no longer be able to connect to the VM local console via the Hyper-V Manager Remote Connection.  You will only be able to connect to the VM via a Remote Desktop connection.  Remove the RemoteFX adapter if you ever need to use the Hyper-V Manager Remote Connection.

**How much does Microsoft Hyper-V Server 2008 R2 SP1 cost? Where can I get it?**

Microsoft Hyper-V Server 2008 R2 SP1 is free and we hope you enjoy it! Here’s the download link: [Microsoft Hyper-V Server 2008 R2 SP1](https://www.microsoft.com/download/details.aspx?id=20196).

Jeff Woolsey

Windows Server & Cloud

\----------------------------------------------------------------

Here are the links to a six part series titled **Dynamic Memory Coming to Hyper-V** and an article detailing 40% greater virtual machine density with DM.

**Part 1: Dynamic Memory announcement**. This blog announces the new Hyper-V Dynamic Memory in Hyper-V R2 SP1. It also discussed the explicit requirements that we received from our customers. [Learn more](https://techcommunity.microsoft.com/t5/virtualization/dynamic-memory-coming-to-hyper-v/ba-p/381719)

**Part 2: Capacity Planning from a Memory Standpoint**. This blog discusses the difficulties behind the deceptively simple question,  “how much memory does this workload require?” Examines what issues our customers face with regard to memory capacity planning and why.  [Learn more](https://techcommunity.microsoft.com/t5/virtualization/dynamic-memory-coming-to-hyper-v-part-2-8230/ba-p/381716)

**Part 3: Page Sharing**. A deep dive into the importance of the TLB, large memory pages, how page sharing works, SuperFetch and more. If you ’re looking for the reasons why we haven’t invested in Page Sharing this is the blog.  [Learn more](https://techcommunity.microsoft.com/t5/virtualization/dynamic-memory-coming-to-hyper-v-part-3-8230/ba-p/381714)

**Part 4: Page Sharing Follow-Up**. Questions answered about Page Sharing and ASLR and other factors to its efficacy. [Learn more](https://techcommunity.microsoft.com/t5/virtualization/dynamic-memory-coming-to-hyper-v-part-4/ba-p/381771)

**Part 5: Second Level Paging**. What it is, why you really want to avoid this in a virtualized environment and the performance impact it can have. [Learn more](https://techcommunity.microsoft.com/t5/virtualization/repost-dynamic-memory-coming-to-hyper-v-part-5-8230/ba-p/381751)

**Part 6: Hyper-V Dynamic Memory**. What it is, what each of the per virtual machine settings do in depth and how this all ties together with our customer requirements. [Learn more](https://techcommunity.microsoft.com/t5/virtualization/dynamic-memory-coming-to-hyper-v-part-6-8230/ba-p/381811)

**Hyper-V Dynamic Memory Density**. An in depth test of Hyper-V Dynamic Memory easily achieving 40% greater density. [Learn more](https://techcommunity.microsoft.com/t5/virtualization/hyper-v-dynamic-memory-test-for-vdi-density/ba-p/381783)
