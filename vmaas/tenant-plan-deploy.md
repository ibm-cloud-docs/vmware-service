---

copyright:

  years: 2022, 2025

lastupdated: "2025-05-23"

keywords: ordering prerequisites, before you order, setup, environment setup

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Planning the deployment
{: #tenant-plan-deploy}

Review the following considerations to plan your {{site.data.keyword.vmware-service_full}} instance deployment.

Review [VMware Cloud Director 10.5 Configuration Limits](https://configmax.broadcom.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.5&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director™.
{: note}

## VMware deployment size
{: #tenant-plan-deploy-vmware-depl}

Consider the size of the VMware® deployment required.

VMware deployment sizings are based on the CPU, memory, and storage that are required to run the targeted workload. If you are planning a workload migration from on-premises to the cloud, the on-premises size is a good starting point. You can resize your VMware deployment at any time.

## {{site.data.keyword.vcf-aas}} type
{: #tenant-plan-deploy-type}

Consider your instance type.

Choose from {{site.data.keyword.vcf-aas-full}} single-tenant or multitenant options. Both single-tenant and multitenant configuration options provide the same experience, security, and reliability for running VMware workloads. The single-tenant option provides the highest level of isolation and consistency.

### {{site.data.keyword.vcf-aas}} single-tenant
{: #tenant-plan-deploy-type-st}

For a dedicated infrastructure and built to order VMware environment, create a **Single-tenant Cloud Director site**. After you create a Cloud Director site, deploy single-tenant virtual data centers (VDCs) with monthly charges for the dedicated VMware infrastructure components.

### {{site.data.keyword.vcf-aas}} multitenant
{: #tenant-plan-deploy-type-mt}

For a flexible, pay-as-you-go VMware environment, create a VDC in a multitenant Cloud Director site. With {{site.data.keyword.cloud_notm}} multitenant, your only step is to create the **Multitenant virtual data center**.

On-demand and reserved pricing plans are available for multitenant instances.

Some data centers are restricted to a specific pricing plan.
{: restriction}

#### On-demand
{: #tenant-plan-deploy-type-mt-ondemand}

For on-demand instances, virtual data center virtual CPU (vCPU) and RAM are allocated as needed. The amount of time that the allocation takes depends on global usage of the virtual data center vCPU and RAM.

* Optionally, set the maximum value limits for the amount of vCPU and RAM that can be used at any time to control costs.
* Increase and decrease the vCPU and RAM resources on a VDC later as required.
* The price is calculated hourly and is based on the resource usage in the VDC.

#### Reserved
{: #tenant-plan-deploy-type-mt-reserved}

For Reserved instances, the vCPU and RAM VDC reservations are pre-allocated and their availability is guaranteed.

* Configure the reserved computing capacity for the VDC.
* Increase and decrease the vCPU and RAM resources on a VDC later as required.
* The price is calculated monthly for the full reservation and is based on the allocation size of the VDC.

## IBM Cloud data center availability
{: #tenant-plan-deploy-locations}

The following data centers are available for {{site.data.keyword.vcf-aas}} deployment.

High availability is supported on a Cloud Director site region only when a Sapphire Rapids server is available.
{: requirement}

| Location | Data center | Single-tenant | Multitenant | Cascade Lake | SAP-certified Cascade Lake | Sapphire Rapids |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
| Sydney | Sydney 01 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} |
| Sydney | Sydney 04 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} |
| Sydney | Sydney 05 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} |
| Tokyo | Tokyo 02 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} |
| Tokyo | Tokyo 04 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} |
| Tokyo | Tokyo 05 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red}|
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for deployment - Asia Pacific" caption-side="bottom"}
{: tab-title="Asia Pacific"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-dc-ap}

| Location | Data center | Single-tenant | Multitenant | Cascade Lake | SAP-certified Cascade Lake | Sapphire Rapids |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
| Frankfurt | Frankfurt 02 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Frankfurt | Frankfurt 04 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Frankfurt | Frankfurt 05 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| London | London 04 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green}[^lon1ST] |
| London | London 05 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| London | London 06 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green}[^lon3ST] |
| Madrid | Madrid 02 | [Yes]{: tag-green} | [Yes]{: tag-green}| [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Madrid | Madrid 04 | [Yes]{: tag-green} | [Yes]{: tag-green}| [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Madrid | Madrid 05 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for deployment - Europe" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-dc-eur}

[^lon1ST]: Single-tenant only

[^lon3ST]: Single-tenant only

| Location | Data center | Single-tenant | Multitenant | Cascade Lake | SAP-certified Cascade Lake | Sapphire Rapids |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
| Dallas | Dallas 10 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
| Dallas | Dallas 12 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
| Dallas | Dallas 13 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
| Toronto | Toronto 01 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Toronto | Toronto 04 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Toronto | Toronto 05 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC | Washington DC 04 | [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC | Washington DC 06 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC | Washington DC 07 | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for deployment - North America" caption-side="bottom"}
{: tab-title="North America"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-northamerica}

## Resource pool
{: #tenant-plan-deploy-rp}

A resource pool combines compute, memory, and storage resources to properly scale your workload requirements.

You can create resource pools across three data centers in the selected multizone region and optionally enable SAP®-certified server profiles of either HANA and NetWeaver or NetWeaver.

To ensure that your applications remain resilient, you can add stretched vSAN™ high availability resource pools to an existing Cloud Director site. The resource pool stretches across two data centers in a multizone region to increase availability and to protect critical workloads from unexpected downtime.

When the high availability resource pool is available, you can create a new single-tenant or multitenant VDC on the stretched resource pool.

Stretched resource pools are available only on some multitenant Cloud Director sites. Additional stretched resource pools will be made available over time.
{: note}

For more information about resource pools, see [Adding resource pools](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

## Cluster
{: #tenant-plan-deploy-cluster}

A resource pool consists of one or more clusters with the following configurations.

### Profile storage types
{: #tenant-plan-deploy-cluster-storage}

For single-tenant Cloud Director sites, you can select NFS only storage or vSAN storage with optional NFS storage.

NFS only clusters do not have local flash storage and cannot be configured for vSAN.

vSAN storage with optional NFS storage is available for instances in locations with 25 GbE availability. vSAN clusters use bare metal host profiles with local flash storage and a RAID 6, FTT=2 policy. This policy is high-performance and high-resilience and requires at least seven hosts. vSAN clusters can also use NFS storage.

High availability resource pools require stretched clusters with vSAN™ storage profiles. NFS storage is not supported.
{: requirement}

The profile storage type depends on the resource pool location. The following options are available for multizone regions.

| Data center | NFS-only storage | vSAN + optional NFS storage |
|:------------|:-----------------|:----------------------------|
| Sydney 01 | [Yes]{: tag-green} | [No]{: tag-red} |
| Sydney 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Sydney 05 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Tokyo 02 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Tokyo 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Tokyo 05 | [Yes]{: tag-green} | [Yes]{: tag-green} |
{: caption="Data center profile storage types - Asia Pacific" caption-side="bottom"}
{: tab-title="Asia Pacific"}
{: tab-group="Multizone profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-prof-asiapacific}

| Data center | NFS-only storage | vSAN + optional NFS storage |
|:------------|:-----------------|:----------------------------|
| Frankfurt 02 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Frankfurt 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Frankfurt 05 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| London 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| London 05 | [Yes]{: tag-green} | [No]{: tag-red} |
| London 06 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Madrid 02 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Madrid 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Madrid 05 | [Yes]{: tag-green} | [Yes]{: tag-green} |
{: caption="Data center profile storage types - Europe" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Multizone profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-prof-europe}

| Data center | NFS-only storage | vSAN + optional NFS storage |
|:------------|:-----------------|:----------------------------|
| Dallas 10 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Dallas 12 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Dallas 13 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Toronto 01 | [Yes]{: tag-green} | [No]{: tag-red} |
| Toronto 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Toronto 05 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC 04 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC 06 | [Yes]{: tag-green} | [Yes]{: tag-green} |
| Washington DC 07 | [Yes]{: tag-green} | [Yes]{: tag-green} |
{: caption="Data center profile storage types - North America" caption-side="bottom"}
{: tab-title="North America"}
{: tab-group="Multizone profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-prof-northamerica}

### Host profile
{: #tenant-plan-deploy-cluster-host}

{{site.data.keyword.cloud_notm}} offers several host profiles to choose from with different sizes and configurations of RAM and CPU. You can select the most optimized host profile to fit the target workloads. When you select a host profile, first assess the types of VMware VMs and workload you plan to run on {{site.data.keyword.vcf-aas}}.

* For migrating workloads into {{site.data.keyword.cloud_notm}}, open source tools such as [RVTools](https://www.robware.net/){: external} build an inventory of the existing VMware environments. [RVTools](https://www.robware.net/) lists all VMs in an existing VMware environment, including the VM CPU, RAM, and storage sizes.
* For new VMware workloads, model out the applications and VM sizes (CPU, RAM, and storage) that you need for each VM.

After you have a list of target VMs including CPU, RAM, and storage requirements, next identify the largest and most important VM applications. When you select a host profile, you want to ensure to use the largest and most important applications to match against the host profile options. Match the largest VM's RAM requirements and CPU requirements against the list of host profiles. As a standard choice, use the host profile with at least as much physical RAM and CPU as the largest VM. It is also important to account for a 10 to 20 % hypervisor overhead.

{{site.data.keyword.vcf-aas}} vCPU is mapped to physical cores at a ration of 2:1. For every one physical core, two vCPUs of compute are assigned.
{: note}

Lastly sum the total RAM, CPU, and storage requirements for all target VMs. The count of hosts multipled by CPU and RAM per host with a multiple of 20% hypervisor overhead provides you with the total number of hosts of the target profile that are required. Also, ensure to factor the size of VDC edges used in the VMware deployment into the total host count calculation.

#### Bare metal server options
{: #tenant-plan-deploy-cluster-host-bms-req}

For single-tenant Cloud Director sites, you can select from various bare metal server CPU and memory sizes based on your selection of location and profile storage type.

Stretched vSAN high availability clusters support only Sapphire Rapids profiles.
{: requirement}

| Profile | Sockets | Cores | RAM | vSAN usable capacity |
|:--------|:--------|:------|:----|:---------------------|
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 15 TB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB | 23 TB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB | 23 TB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 23 TB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB | 38 TB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB | 38 TB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 46 TB |
| Dual Intel 6416H Xeon[^esa61h] | 2 | 36 | 1024 GB | 61 TB |
| Dual Intel 6416H Xeon[^esa122h] | 2 | 36 | 1024 GB | 122 TB |
| Dual Intel 6416H Xeon[^esa184h] | 2 | 36 | 1024 GB | 184 TB |
| Quad Intel 8260 Xeon | 4 | 96 | 1536 GB | 61 TB |
| Dual Intel 8474C Xeon | 2 | 96 | 2048 GB | 6 TB |
| Dual Intel 8474C Xeon | 2 | 96 | 2048 GB | 13 TB |
| Dual Intel 8474C Xeon | 2 | 96 | 2048 GB | 31 TB |
| Dual Intel 8474C Xeon[^esa61] | 2 | 96 | 2048 GB | 61 TB |
| Dual Intel 8474C Xeon[^esa122] | 2 | 96 | 2048 GB | 122 TB |
| Dual Intel 8474C Xeon[^esa184] | 2 | 96 | 2048 GB | 184 TB |
{: caption="Available vSAN host profiles" caption-side="bottom"}
{: tab-title="vSAN clusters"}
{: tab-group="Host profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-vsan-hp}

[^esa61]: Applicable to vSAN ESA profiles

[^esa122]: Applicable to vSAN ESA profiles

[^esa184]: Applicable to vSAN ESA profiles

[^esa61h]: Applicable to vSAN ESA profiles

[^esa122h]: Applicable to vSAN ESA profiles

[^esa184h]: Applicable to vSAN ESA profiles

| Profile | Sockets | Cores | RAM |
|:--------|:--------|:------|:----|
| Dual Intel 5218 Xeon | 2 | 32 | 192 GB |
| Dual Intel 5218 Xeon | 2 | 32 | 384 GB |
| Dual Intel 6248 Xeon | 2 | 40 | 384 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 384 GB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB |
| Dual Intel 6416H Xeon[^esa1024] | 2 | 36 | 1024 GB |
| Quad Intel 8260 Xeon | 4 | 96 | 1536 GB |
| Dual Intel 8474C Xeon[^esa2048] | 2 | 96 | 2048 GB |
{: caption="Available NFS-only host profiles" caption-side="bottom"}
{: tab-title="NFS-only clusters"}
{: tab-group="Host profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-nfs-hp}

[^esa1024]: Applicable to vSAN ESA profiles

[^esa2048]: Applicable to vSAN ESA profiles

#### Performance characteristics
{: #tenant-plan-deploy-cluster-perf}

For single-tenant Cloud Director sites, you can select from the following storage performance tiers.

* 0.25 IOPS/GB
* 2 IOPS/GB
* 4 IOPS/GB
* 10 IOPS/GB

For NFS only storage, you must select at least one unit of 2 IOPS/GB or higher.
{: requirement}

## Fast provisioning of virtual machines
{: #tenant-plan-deploy-fast-provisioning}

For VDC orders, you can enable fast provisioning for any VDC created within the resource pool.

Fast provisioning saves time by using linked clones for VM provisioning. If not enabled, all provisioning operations use full clones. When fast provisioning is enabled, VM deployment time that uses Director catalog images can be 10 times faster or more.

In-place consolidation of a fast-provisioned VM is not supported. As the number of linked clones grows, VM execution performance can be impacted.
{: important}

When you create your VDC and it is in **Available** status, you can enable or disable fast provisioning from the **Summary** tab in the VDC details page.

### Linked clones
{: #tenant-plan-deploy-fast-provisioning-linked}

A linked clone is a snapshot of a VM that shares virtual disks with the parent VM in an ongoing manner. This conserves disk space and allows multiple VMs to use the same software installation. Linked clones make it easier to create unique VMs for individual tasks. Linked clones are also easier to share among Support and Development teams who need access to the same virtual disks.

The disadvantage of a linked clone is that it must maintain access to the parent VM. The VM that first created the clone cannot be deleted unless all linked clones are also deleted.

### Full clones
{: #tenant-plan-deploy-fast-provisioning-full}

A full clone is a complete and independent copy of a VM and operates separately from the original parent VM. Because they do not share virtual disks with the original parent VM, full clones generally perform better than linked clones. However, they also take longer to create than linked clones. ‍

## Network settings
{: #tenant-plan-deploy-network}

For Cloud Director sites, you can select from public and private options for management and workload connectivity.

### Management connectivity
{: #tenant-plan-deploy-network-mgmt}

Management connectivity determines how you connect to the VMware Cloud Director UI or API and the Veeam® Backup service. You can access the management interfaces only from a source in the {{site.data.keyword.cloud_notm}} network. For private-only management network settings, you can create an ingress allowlist to allow connections from source subnets.

Select either public-only or private-only management connectivity.

### Workload connectivity
{: #tenant-plan-deploy-network-wkload}

Workload connectivity determines how you connect to your {{site.data.keyword.vcf-aas}} virtual machines (VMs) and vApps. Select either public and private or private-only workload connectivity.

When you select private-only workload connectivity for your Cloud Director site, all VDCs deployed in that site are private-only workloads. These VDCs do not have an incoming or outgoing connectivity path to the public internet and can access {{site.data.keyword.cloud_notm}} Services only over the private {{site.data.keyword.IBM_notm}} network.

You can connect VDCs to {{site.data.keyword.tg_full_notm}} to enable the workloads to securely connect to other workloads outside of the private network or are alternatively sandboxed in the VDC. For more information, see [Using Transit Gateway to interconnect {{site.data.keyword.vcf-aas}} with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections).

## Network edge
{: #tenant-plan-deploy-nwedge}

VDCs connect to the public and IBM private networks through high availability edges. Edges can also be used to connect multiple VDC networks together. You can create your VDC with or without a network edge.

You can optionally deploy a regional high availability edge either on a stretched resource pool or across two resource pools in a multizone region. For network regional high availability, a dedicated network edge and a private-only connection are required for multizone availability. 

### Network edge location
{: #tenant-plan-deploy-edge-location}

For a regional high availability edge on a stretched workload cluster, you can swap the primary and secondary network location.

For a regional high availability edge on an unstretched workload cluster, the primary network resource pool location is determined by the VDC location by default. You select the secondary network resource pool location.

### Network edge connection
{: #tenant-plan-deploy-edge-connection}

When you create your VDC with a network edge, you can select either a public and private network connection or a private-only network connection. If the Cloud Director site has a private-only connection, private-only is the only available option for the VDC network edge.

A private-only connection is required for network regional high availability. Private-only edges require connectivity to an {{site.data.keyword.cloud_notm}} Transit Gateway for inbound and outbound networking from the VDC.

### Network edge type
{: #tenant-plan-deploy-edge}

NSX Edge performance is coupled to the CPU available to the edge. Network IO amounts, including inbound and outbound traffic, in addition to use of edge services directly impact edge use of CPU. The larger edge sizes provide more CPU resource for the edge.

| Edge type | Details |
|:--------- |:------- |
| Shared | This option is suitable for saving resources and costs for development and proof-of-concept scenarios and is not recommended for use in production scenarios.  \n  Provides a low-cost and lower-performing solution where a single edge is shared by up to 64 VDCs. Network performance can be inconsistent with multiple VDCs that use the same infrastructure and compete for networking bandwidth. In addition, edge services such as VPN, Firewall, NAT, and routing further use edge resources and can degrade performance in a shared edge configuration.  \n  A shared edge does not provide a performance upgrade option. |
| Dedicated - M | This dedicated edge option is suitable for smaller production deployments with fewer networking demands.  \n  Provides an edge that is dedicated to a single VDC. Networking bandwidth is consistent and supports traffic performance up to 6 Gbps and supports edge services such as VPN, Firewall, NAT, and routing. |
| Dedicated - L | The recommended dedicated edge option for large production workloads and high traffic.  \n Provides an edge that is dedicated to a single VDC and consistent networking bandwidth to support traffic performance up to 10 Gbps while also supporting edge services such as VPN, Firewall, NAT, and routing. |
| Dedicated - XL | This dedicated edge option is suitable for the most demanding networking requirements.  \n Supports the highest level of edge services and throughput over 10 Gbps.  |
{: caption="Network edge descriptions" caption-side="bottom"}  

High inbound traffic from the public internet can trigger {{site.data.keyword.cloud_notm}}'s network protection platform. Contact IBM Support to discuss options for your network protection setting if you anticipate high inbound rates. For more information, see [Understanding network protection](/docs/subnets?topic=subnets-understanding-network-protect).
{: note}

## Services for {{site.data.keyword.vcf-aas}}
{: #tenant-plan-deploy-services}

The following add-on services are optionally available for {{site.data.keyword.vcf-aas}} Cloud Director site instances.

### Veeam Backup
{: #tenant-plan-deploy-services-veeam}

For single-tenant instances, the Veeam Backup service is included by default with your Cloud Director site instance order. You can optionally remove the service before you create your instance. Service charges are incurred only if you choose to include the service in your order. You can add or remove the service later as required.

For multitenant instances, the Veeam Backup service is deployed on the Cloud Director site to provide VDCs with data recovery. If you want to use the service, you must install it after you create a multitenant VDC. Service charges are incurred only if you choose to install the service.

### VMware Cloud Director Availability
{: #tenant-plan-deploy-services-vcda}

Use the enterprise-level VMware Cloud Director Availability (VCDA) service to migrate and protect VMs and vAPPS over a secure public internet connection.

The VCDA service is optionally included at no charge with your single-tenant Cloud Director site instance order. You can remove the service before you create your instance. You can add or remove the service later as required.

The VCDA service is included as a default option in multitenant VDC orders.

For a VCDA *disaster recovery* configuration, a monthly charge is incurred per protected VM.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
