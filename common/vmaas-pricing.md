---

copyright:
 
  years: 2025

lastupdated: "2025-08-06"

keywords: VMware Cloud Foundation as a Service pricing, VCF as a Service pricing, pricing plan

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vcf-aas}} pricing
{: #vmaas_pricing}

{{site.data.keyword.vmware-service_full}} compute resources are available as either a single-tenant or multitenant model.

The {{site.data.keyword.vcf-aas-full}} single-tenant model offers dedicated hosts that are managed by your organization. First, you order a {{site.data.keyword.vcf-aas}} single-tenant Cloud Director site then you create one or more virtual data centers (VDCs) where you deploy your virtual machines (VMs).

For the multitenant model, {{site.data.keyword.IBM}} hosts and operates a resource pool where you order virtual resources as needed. {{site.data.keyword.IBM_notm}} manages your capacity, performance, and hardware upgrades. When you order a multitenant instance, you select the location to create a VDC in an existing Cloud Director site.

On the **{{site.data.keyword.vmware-service_short}}** order page, click [See pricing details](/vmware/vmware_as_a_service/provision/vdc_st) to view the rate card that outlines cost details by feature.
{: note}

## Understanding billing terminology
{: #vmaas_pricing-term}

### Usage
{: #vmaas_pricing-term-usage}

Metering determines how {{site.data.keyword.IBM_notm}} counts usage for the full potential size of the resource for the time period that the resource is used.

For example, a single-zone on-demand VDC is created with a resource limit of 100 virtual CPU (vCPU) and 800 GB RAM. The data center has no VMs running on it, so you do not receive a charge for the vCPU and RAM. If an 8 vCPU with 8 GB virtual machine (VM) is started, metering is calculated for the size of that VM. If the VM uses fewer resources than the ones assigned to it, metering is applicable to the full size of the VM.

### Allocation
{: #vmaas_pricing-term-alloc}

{{site.data.keyword.IBM_notm}} bills based on the resources that you allocate when you provision an instance. The allocated resources are guaranteed.

Metering is applicable to the full potential size of the resource for the life of the resource.

For example, a single-zone reserved VDC is created with a resource allocation of 100 vCPU and 800 GB RAM and no VMs are created or running on it. Metering is applicable to 100 vCPU and 800 GB RAM.

### Peak metric usage
{: #vmaas_pricing-term-metric}

The metric displays on your bill as either monthly peak metric usage or hourly peak metric usage.

*Monthly peak usage* is the maximum value of the metric that is used over a full month. For example, a single-zone reserved VDC is created with 100 vCPU and 800 GB RAM. Later in the month, the data center is reduced to 50 vCPU and 400 GB RAM. The monthly peak usage is 100 vCPU and 800 GB RAM.

*Hourly peak usage* is the maximum value of the metric that is used over an hour. For example, if 100 vCPU is used for a minute of the hour with 0 vCPU used for the other 59 mins, the hourly peak metric usage is 100 vCPU.

View service billing and usage details in the VMware Solutions console. Click **Manage > Billing and usage** to review the service usage and charges. In the **Billing and usage** view, locate the **VMware Cloud Foundation as a Service** service type. Then, locate the **Organization** plan to find the service usage across all VDCs in that organization. For multitenant models, VDC usage is located in a separate plan for either the on-demand or the reserved pricing plan. 
{: note}

## Billing considerations for single-tenant models
{: #vmaas_pricing-single} 

Review minimum order requirements and storage considerations for single-tenant models.

Minimum 2 servers (minimum 7 servers for vSAN™ profiles)
 * 2 hosts (2-socket 32 cores, 192 GB RAM)
 * 24 TB of shared storage
 * Minimum of 1 VDC with a Medium Dedicated Edge

With a seven host minimum with vSAN profiles, a high availability standard with FTT=2 and RAID6 ensures that a system can tolerate multiple failures during a maintenance event with no data loss. Consider the overhead that you must incorporate when you determine the amount of storage to provision.

Storage that is ordered after the first day of the month is prorated for the first month. Storage that is removed during the month is charged for the full month that it is removed. Each storage change is treated individually. For example, when you remove storage then add storage, the bill reflects both storages for that month. For vSAN host profiles, the profile name displays the total of both raw and the usable storage.

| Feature | Billing model |
|:--------|:--------------|
| Host profiles | Size for bare metal server profiles including sockets, core, and RAM. \n - Hosts are billed monthly. \n - Hosts that you order after the first day of the month are prorated for the first month. \n - Hosts that are removed during the month are charged for the full month that they are removed. \n - Each host is treated individually. For example, when you remove a host then add a host, the bill reflects two hosts for that month. |
{: caption="Single-tenant instance billing" caption-side="bottom"}
{: tab-title="Compute"}
{: tab-group="Single-tenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-st-compute}

| Feature | Metrics | Billing model  |
|:--------|:--------|:---------------|
| NFS Shared Storage at 0.25 IOPS/GB | TOTAL_STORAGE_POINT_TWO_FIVE_IOPS_GB | The peak storage **allocation** at the 0.25 IOPS/GB tier over the period of a month. |
| NFS Shared Storage at 2.0 IOPS/GB | TOTAL_STORAGE_TWO_IOPS_GB | The peak storage **allocation** at the 2 IOPS/GB tier over the period of a month. |
| NFS Shared Storage at 4.0 IOPS/GB | TOTAL_STORAGE_FOUR_IOPS_GB | The peak storage **allocation** at the 4 IOPS/GB tier over the period of a month. |
| NFS Shared Storage at 10 IOPS/GB | TOTAL_STORAGE_TEN_IOPS_GB | The peak storage **allocation** at the 10 IOPS/GB tier over the period of a month. |
{: caption="Single-tenant instance billing" caption-side="bottom"}
{: tab-title="Storage"}
{: tab-group="Single-tenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-st-storage}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| Network edge storage | | Shared edge storage with egress pricing and billed separately. \n - Edge storage is billed monthly.\n - Edges that are ordered after the first day of the month are prorated for the first month. \n - Edges that are removed during the month are charged for the full month that they are removed. \n - Each edge change is treated individually. For example, when you remove an edge then add an edge, the bill reflects both edges for that month. \n - For an efficiency edge, one edge instance is used with 1-64 VRF (virtual edges). One efficiency edge can support up to 64 virtual data centers (VDCs) until the next edge instance is deployed. When an efficiency edge reaches attachment of zero VDCs the efficiency edge is removed. |
| Total egress | TOTAL_EGRESS_GB | Total outbound public networking from all virtual data centers. |
| Private service endpoint | MAX_PRIVATE_NETWORK_ONE_G_COST \n MAX_PRIVATE_NETWORK_TEN_G_COST | Monthly charge for dedicated 1 or 10 GB uplinks for the Cloud Director UI and API private network access. |
{: caption="Single-tenant instance billing" caption-side="bottom"}
{: tab-title="Networking"}
{: tab-group="Single-tenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-st-network}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| Veeam Backup service base | | Monthly managed Veeam service base charge for every instance. |
| Veeam Backup service host | | Monthly Veeam proxy storage cost for every host. |
| Veeam license | MAX_VEEAM_LICENSES | Veeam license charge for every VM under backup. Monthly charge for the highest number of VMs under backup at any time period in the month. |
| Veeam block storage | TOTAL_VEEAM_BLOCK_STORAGE_GB_HOURS | Hourly charge per GB of block storage used for all backups. Initially, all Veeam backups go to the {{site.data.keyword.blockstorageshort}} that is closest to their VM workloads. Backups that are a part of an inactive backup chain are immediately moved to {{site.data.keyword.cloud_notm}} Object Storage. The restore speed for these inactive backups might be impacted. You can change how fast the inactive backup chains are moved to {{site.data.keyword.cloud_notm}} Object Storage by opening an {{site.data.keyword.vcf-aas}} service ticket. For more information, see [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam). |
| Veeam object storage | TOTAL_VEEAM_OBJECT_STORAGE_GB_HOURS | Hourly charge per GB of object storage used for all backups. |
{: caption="Single-tenant instance billing" caption-side="bottom"}
{: tab-title="Backup"}
{: tab-group="Single-tenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-st-veeam}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| VCDA Disaster Recovery license| DEDICATED-VCDA-DR-LICENSES | Monthly VMware Cloud Director Availability (VCDA) disaster recovery license charge for every protected VM. \n A VCDA VM Migration license is optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge.|
| VCDA 20 GB private service endpoint | VCDA-PRIVATE-SERVICE-ENDPOINT |  Monthly charge for every instance endpoint with a private connection. |
{: caption="Single-tenant instance billing" caption-side="bottom"}
{: tab-title="Migration and DR"}
{: tab-group="Single-tenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-st-vcda}

## Billing considerations for multitenant models
{: #vmaas_pricing-multi}

{{site.data.keyword.vcf-aas}} offers two pricing plans for creating multitenant VDCs: **On-demand** and **Reserved**. 
 
For on-demand instances, virtual data center vCPU and RAM are allocated as needed. Pricing is hourly based on the resource usage in the VDC. The amount of time that the allocation takes depends on global usage of the virtual data center vCPU and RAM. Set the maximum value limits for vCPU and RAM.

For reserved instances, the vCPU and RAM VDC reservations are pre-allocated and their availability is guaranteed. Pricing is monthly based on the allocation size of the VDC.

For both on-demand and reserved plans, you can increase and decrease the vCPU and RAM resources on a VDC later as required.

Storage quantity includes all storage that is allocated per VM, even if the VM is stopped, and all VM snapshots. Storage usage increases with new VMs and snapshots and decreases when VMs and snapshots are removed.

Storage policy availability can vary by region and deployment topology.

| Feature | Metrics | Billing model |
|:--------|:-------|:--------------|
| **On-demand** vCPU | TOTAL_VCPU_HOURS | The peak vCPU **usage** over the period of an hour. \n - vCPU is billed hourly. \n -  vCPU quantity is for all vCPU allocated to all running VMs in the VDC at any time per hour. \n - When a VM is stopped it is not counted in the total vCPU calculation. For example, if two running VMs both have 4 vCPU, then a third VM is started at 4 vCPU. The vCPU for the one hour period is 12 vCPU. |
| **On-demand** RAM | TOTAL_RAM_GB_HOURS | The peak memory **usage** over the period of an hour. \b - RAM is billed hourly. \n - RAM quantity is for all RAM allocated to all running VMs in the VDC at any time per hour. \n -  When a VM is stopped it is not counted in the total RAM calculation. For example, if two running VMs have 16 GB RAM, then a third VM is started also at 16 GB RAM. The RAM for the one hour period is 48 GB. |
| Multizone **On-demand** vCPU | | - vCPU is billed hourly. \n - vCPU quantity supports vCPU in both (2) of the data centers for all vCPU allocated to all running VMs in the VDC at any time per hour. \n - The vCPU size is double the cost of your order to support the vCPU in both data centers. For example, if the VM has 4 vCPU and runs in a multizone region, then the total vCPU is 8. \n - You can see the amount of vCPU that the VM uses in the primary region and {{site.data.keyword.IBM_notm}} allocates the same amount of vCPU in the secondary region. |
| Multizone **On-demand** RAM | | - RAM is billed hourly.  \n - RAM quantity supports RAM in both (2) of the data centers for all RAM allocated to all running VMs in the VDC at any time per hour. \n - The RAM size is double the cost of your order to support the RAM in both data centers. For example, if the VM has 16 GB RAM in a multizone region, then the total is 32 GB RAM. \n - You can see the amount of RAM that the VM uses in the primary region and {{site.data.keyword.IBM_notm}} allocates the same amount of RAM in the secondary region. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Compute: On-demand"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-compute-od}

| Feature | Metrics | Billing model |
|:--------|:-------|:--------------|
| **Reserved** vCPU | MAX_VCPU | The peak vCPU **allocation** for the VDC over the period of one month. The peak vCPU metric is determined by the largest vCPU reservation value that is selected by the customer over a one month period. \n - vCPU is billed monthly for the highest capacity reservation set for that month. \n - VDC reservations are prorated for the first month. If the reservation is increased, then decreased again, the high water mark vCPU capacity reservation is charged for that month. |
| **Reserved** RAM | MAX_RAM_GB | The peak memory **allocation** for the VDC over the period of one month. The peak memory metric is determined by the largest memory reservation value that is selected by the customer over a one month period. \n - RAM is billed monthly for the highest capacity reservation set for that month. \n - VDC reservations are prorated for the first month. If the reservation is increased, then decreased again, the high water mark RAM capacity reservation is charged for that month. |
| Multizone **Reserved** vCPU | | - vCPU is billed monthly for the highest capacity reservation set for that month. \n - The vCPU size is double the cost of your reservation to support the vCPU in both data centers.  For example, if the VM has 4 vCPU reserved in a multizone region, then the total reserved vCPU is 8. \n - You can see the amount of vCPU that the VM uses in the primary region and {{site.data.keyword.IBM_notm}} allocates the same amount of vCPU in the secondary region. |
| Multizone **Reserved** RAM | | - RAM is billed monthly for the highest capacity reservation set for that month. \n - The RAM size is double the cost of your reservation to support the RAM in both data centers.  For example, if the VM has 16 GB RAM reserved in a multizone region, then the total reservation is 32 GB RAM. \n - You can see the amount of RAM that the VM uses in the primary region and {{site.data.keyword.IBM_notm}} allocates the same amount of RAM in the secondary region. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Compute: Reserved"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-compute-reserved}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| NFS Shared Storage at 0.25 IOPS/GB | TOTAL_STORAGE_POINT_TWO_FIVE_IOPS_GB_HOURS | The peak storage **allocation** at the 0.25 IOPS/GB tier over the period of an hour. |
| NFS Shared Storage at 2.0 IOPS/GB | TOTAL_STORAGE_TWO_IOPS_GB_HOURS | The peak storage **allocation** at the 2 IOPS/GB tier over the period of an hour. |
| NFS Shared Storage at 4.0 IOPS/GB | TOTAL_STORAGE_FOUR_IOPS_GB_HOURS | The peak storage **allocation** at the 4 IOPS/GB tier over the period of an hour. |
| NFS Shared Storage at 10 IOPS/GB | TOTAL_STORAGE_TEN_IOPS_GB_HOURS | The peak storage **allocation** at the 10 IOPS/GB tier over the period of an hour. |
| VMware vSAN storage | TOTAL_STORAGE_VSAN_GB_HOURS | The peak vSAN storage **allocation** over the period of an hour. |
| VMware standard storage | | The peak standard storage **allocation** over the period of an hour. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Storage"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-storage}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| Windows license | MAX_WINDOWS_LICENSES | The hourly peak number of Windows® license **usage** based on Windows VM vCPU size. For example, if you have two Windows VMs, one VM with 16 vCPU and one VM with 8 vCPU, the usage is 24 vCPU of Windows license usage. |
| Red Hat Enterprise Linux (over 127 vCPU) license | TOTAL_RHEL_LARGE_LICENSES | The hourly peak number of RHEL license usage based on VM vCPU size. One license is charged per vCPU. Large RHEL VMs are larger than 127 vCPUs. |
| Red Hat Enterprise Linux (9-127 vCPU) license | TOTAL_RHEL_MID_LICENSES	| The hourly peak number of RHEL license usage based on VM vCPU size. One license is charged per vCPU. Mid RHEL VMs are between 9 and 127 vCPUs. |
| Red Hat Enterprise Linux (up to 8 vCPU) license | TOTAL_RHEL_SMALL_LICENSES | The hourly peak number of RHEL license usage based on VM vCPU size. One license is charged per vCPU. Small RHEL VMs are 8 vCPUs or smaller. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="OS"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-os}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| Network edge | |  \n - Multiple edge storage options: shared and dedicated medium, large, or extra large \n - Edges are billed monthly based on the type of edge used. The efficiency edge is the most cost-effective edge and the extra large edge provides the highest level of edge services and throughput over 10 Gbps. \n - Edges are prorated for the first month. \n - Each edge change is treated individually. For example, when you remove an edge then add an edge, the bill reflects both edges for that month. \n - {{site.data.keyword.IBM_notm}} recommends the **Dedicated - L** edge for large production workloads and high traffic. For more information, see [Network edge type](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-edge). |
| Edge gateway traffic | TOTAL_EGRESS_GB | The **total** outbound public traffic is charged per GB transferred over the period of one month. This value includes the outbound traffic through the VDC NSX edge to the public internet. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Network"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-network}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| Veeam license | MAX_VEEAM_LICENSES | Veeam Backup service license charge for every VM under backup. Monthly charge for the highest number of VMs under backup at any time period in the month. |
| Veeam block storage | TOTAL_VEEAM_BLOCK_STORAGE_GB_HOURS | Hourly charge per GB of block storage used for all backups. Initially, all Veeam backups go to the {{site.data.keyword.blockstorageshort}} that is closest to their VM workloads. Backups that are a part of an inactive backup chain are immediately moved to {{site.data.keyword.cloud_notm}} Object Storage. The restore speed for these inactive backups might be impacted. You can change how fast the inactive backup chains are moved to {{site.data.keyword.cloud_notm}} Object Storage by opening an {{site.data.keyword.vcf-aas}} service ticket. For more information, see [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam). |
| Veeam object storage | TOTAL_VEEAM_OBJECT_STORAGE_GB_HOURS | Hourly charge per GB of object storage used for all backups. |
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Backup"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-veeam}

| Feature | Metrics | Billing model |
|:--------|:--------|:--------------|
| VCDA Disaster Recovery license| DEDICATED-VCDA-DR-LICENSES | Monthly VMware Cloud Director Availability (VCDA) disaster recovery license charge for every protected VM. \n A VCDA VM Migration license is optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge.|
{: caption="Multitenant instance billing" caption-side="bottom"}
{: tab-title="Migration and DR"}
{: tab-group="Multitenant billing"}
{: class="simple-tab-table"}
{: #simpletabtable-mt-vcda}

## Related links
{: #vmaas_pricing-related}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [VMware Cloud Director Tenant Guide](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director/vmware-cloud-director/10-5/map-for-vmware-cloud-director-tenant-portal-guide-10-5.html){: external}
* [Troubleshooting NSX Edge](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/installation-guide/troubleshooting-installation-issues/troubleshooting-nsx-edge-nodes.html){: external}
