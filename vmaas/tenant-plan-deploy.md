---

copyright:

  years:  2022, 2023

lastupdated: "2023-10-25"

keywords: ordering prerequisites, before you order, setup, environment setup

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Planning the deployment
{: #tenant-plan-deploy}

Before you order an {{site.data.keyword.vmware-service_full}} instance, ensure that you plan your deployment.

## VMware deployment size
{: #tenant-plan-deploy-vmware-depl}

Consider the size of the VMware® deployment required.

VMware deployments are sized based on the CPU, memory, and storage that are required to run the targeted workload. If you are planning a workload migration from on-premises to the cloud, the on-premises size is a good starting point. You can resize your VMware deployment at any time.

## {{site.data.keyword.vmware-service_short}} type
{: #tenant-plan-deploy-type}

Consider your instance type.

Choose from single-tenant or multitenant options. Both single-tenant and multitenant configuration options provide the same experience, security, and reliability for running VMWare Workloads. The single-tenant option provides the highest level of isolation and consistency.

### {{site.data.keyword.vmware-service_short}} single-tenant
{: #tenant-plan-deploy-type-st}

For a dedicated infrastructure and built to order VMware environment, create a single-tenant Cloud Director site. After you create a Cloud Director site, deploy virtual data centers (VDCs) with monthly charges for the dedicated VMware infrastructure components.

### {{site.data.keyword.vmware-service_short}} multitenant
{: #tenant-plan-deploy-type-mt}

For a flexible, pay-as-you-go VMware environment, create a VDC in a multitenant Cloud Director site. With {{site.data.keyword.vmware-service_short}} multitenant, your only step is to create the Cloud Director VDC.

On-demand and reserved pricing plans are available for multitenant instances.

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

The following {{site.data.keyword.cloud_notm}} data centers are available for {{site.data.keyword.vmware-service_short}} deployment.

| Location | Data center | Type |
|:----------|:----------|:------|
| Frankfurt | Frankfurt 02 | Single-tenant and Multitenant |
| Frankfurt | Frankfurt 04 | Single-tenant and Multitenant |
| Frankfurt | Frankfurt 05 | Single-tenant and Multitenant |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-eur}

| Location | Data center | Type |
|:----------|:----------|:------|
| Dallas | Dallas 10 | Single-tenant and Multitenant |
| Dallas | Dallas 12 | Single-tenant and Multitenant |
| Dallas | Dallas 13 | Single-tenant and Multitenant |
| Washington DC | Washington DC 04 | Single-tenant and Multitenant |
| Washington DC | Washington DC 06 | Single-tenant and Multitenant |
| Washington DC | Washington DC 07 | Single-tenant and Multitenant |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="North America"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-northamerica}

## Fast provisioning of virtual machines
{: #tenant-plan-deploy-fast-provisioning}

Fast provisioning saves time by using linked clones for virtual machine (VM) provisioning. You can enable fast provisioning for any VDC created within the PVDC. If not enabled, all provisioning operations use full clones. When fast provisioning is enabled, VM deployment time that uses Director catalog images can be 10 times faster or more.

In-place consolidation of a fast-provisioned VM is not supported. As the number of linked clones grow, VM execution performance can be impacted.
{: important}

You can enable fast provisioning during your instance order and from the **Data center details** page when the VDC is in **Available** status.

## Network edge type
{: #tenant-plan-deploy-edge}

VDCs connect to the public and IBM private networks through edges. Edges can also be used to connect multiple VDC networks together. You can create your VDC with or without a network edge. Network edge types include: Efficiency, Performance - M, Performance - L, and Performance - XL.

| Edge type | Details |
|:--------- |:------- |
| Efficiency | These edges allocate networking resources that can be used by up to 100 VDCs before another efficiency edge needs to be created. The first time an efficiency edge is selected new CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. Subsequent VDCs up to 100 can use this edge at no extra cost. This option is suitable for saving resources and costs with independent networking control per VDC. |
| Performance - M | This option is suitable when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput requirement is less than 2 Gbps. |
| Performance - L | This option is suitable when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput is in the range 2 - 10 Gbps. |
| Performance - XL | This option is suitable when the total throughput required is multiple Gbps for L7 and VPN. |
{: caption="Table 2. Network edge descriptions" caption-side="bottom"}

## Profile storage type
{: #tenant-plan-deploy-storage}

For single-tenant Cloud Director sites, you can select NFS only storage or vSAN™ storage with optional NFS storage.

NFS only clusters do not have local flash storage and cannot be configured for vSAN.

vSAN storage with optional NFS storage is available for instances in locations with 25 GbE availability. vSAN clusters use bare metal host profiles with local flash storage and a RAID 6, FTT=2 policy. This is a high-performance and high-resilience policy, and it requires at least 7 hosts. vSAN clusters can also use NFS storage.

If you want to save storage space, you can enable vSAN deduplication and compression to reduce redundant data within each disk group. This option can increase overall storage space based on the data type.

The vSAN deduplication and compression option is available for enablement only when you order a single-tenant cluster.
{: note}

## Bare metal server requirements
{: #tenant-plan-deploy-bms-req}

For single-tenant Cloud Director sites, you can select from various bare metal server CPU and memory sizes based on your selection of location and profile storage type.

For vSAN clusters, you can select Dual Intel® 8260 Xeon® (2 Sockets - 48 Cores, 768 GB RAM) with either 15 TB, 23 TB, or 46 TB of vSAN usable capacity.

The following options are available for NFS only clusters.

* Dual Intel 5218 Xeon (2 Sockets - 32 Cores, 192 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 384 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 768 GB RAM)
* Dual Intel 8260 Xeon (4 Sockets - 96 Cores, 1536 GB RAM)

## Performance characteristics
{: #tenant-plan-deploy-perf-char}

For single-tenant Cloud Director sites, you can select from the following storage performance tiers.

* 0.25 IOPS/GB
* 2 IOPS/GB
* 4 IOPS/GB
* 10 IOPS/GB

For NFS only storage, you must select at least one unit of 2 IOPS/GB or higher.
{: requirement}

## Services for {{site.data.keyword.vmware-service_short}}
{: #tenant-plan-deploy-services}

The following add-on services are optionally available for {{site.data.keyword.vmware-service_short}} Cloud Director site instances.

### Veeam Backup and Replication
{: #tenant-plan-deploy-services-veeam}

For single-tenant instances, the Veeam® Backup and Replication service is included by default with your Cloud Director site instance order. You can optionally remove the service before you create your instance. Service charges are incurred only if you choose to include the service in your order. You can add or remove the service later as required.

For multitenant instances, the Veeam Backup and Replication service is deployed on the VMware Cloud Director site to provide VDCs with data recovery. If you want to use the service, you must install it after you provision your virtual data center (VDC). Service charges are incurred only if you choose to install the service.

### VMware Cloud Director Availability
{: #tenant-plan-deploy-services-vcda}

For single-tenant instances, the VMware Cloud Director Availability service is included at no charge by default with your Cloud Director site instance order. You can optionally remove the service before you create your instance. You can add or remove the service later as required.

## Configuration limits for VMware Cloud Director
{: #tenant-plan-deploy-cloud-dir-limits}

Review [VMware Cloud Director 10.4 Configuration Limits](https://configmax.esp.vmware.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.4&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director™.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering-mt)
