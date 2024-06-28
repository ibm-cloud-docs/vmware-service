---

copyright:

  years:  2022, 2024

lastupdated: "2024-06-28"

keywords: ordering prerequisites, before you order, setup, environment setup

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Planning the deployment
{: #tenant-plan-deploy}

Review the following considerations to plan your {{site.data.keyword.vmware-service_full}} instance deployment.

Review [VMware Cloud Director 10.5 Configuration Limits](https://configmax.esp.vmware.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.5&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director™.
{: note}

## VMware deployment size
{: #tenant-plan-deploy-vmware-depl}

Consider the size of the VMware® deployment required.

VMware deployment sizings are based on the CPU, memory, and storage that are required to run the targeted workload. If you are planning a workload migration from on-premises to the cloud, the on-premises size is a good starting point. You can resize your VMware deployment at any time.

## {{site.data.keyword.vcf-aas}} type
{: #tenant-plan-deploy-type}

Consider your instance type.

Choose from single-tenant or multitenant options. Both single-tenant and multitenant configuration options provide the same experience, security, and reliability for running VMWare workloads. The single-tenant option provides the highest level of isolation and consistency.

### {{site.data.keyword.vcf-aas}} single-tenant
{: #tenant-plan-deploy-type-st}

For a dedicated infrastructure and built to order VMware environment, create a single-tenant Cloud Director site. After you create a Cloud Director site, deploy virtual data centers (VDCs) with monthly charges for the dedicated VMware infrastructure components.

### {{site.data.keyword.vcf-aas}} multitenant
{: #tenant-plan-deploy-type-mt}

For a flexible, pay-as-you-go VMware environment, create a VDC in a multitenant Cloud Director site. With {{site.data.keyword.vcf-aas-full}} multitenant, your only step is to create the Cloud Director VDC.

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

The following {{site.data.keyword.cloud_notm}} data centers are available for {{site.data.keyword.vcf-aas}} deployment.

| Location | Data center | Type |
|:----------|:----------|:------|
| Tokyo | Tokyo 02 | Single-tenant |
| Tokyo | Tokyo 04 | Single-tenant |
| Tokyo | Tokyo 05 | Single-tenant |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="Asia-Pacific"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-dc-ap}

| Location | Data center | Type |
|:----------|:----------|:------|
| Frankfurt | Frankfurt 02 | Single-tenant and Multitenant |
| Frankfurt | Frankfurt 04 | Single-tenant and Multitenant |
| Frankfurt | Frankfurt 05 | Single-tenant |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-dc-eur}

| Location | Data center | Type |
|:----------|:----------|:------|
| Dallas | Dallas 10 | Single-tenant and Multitenant |
| Dallas | Dallas 12 | Single-tenant and Multitenant |
| Dallas | Dallas 13 | Single-tenant |
| Washington DC | Washington DC 04 | Single-tenant |
| Washington DC | Washington DC 06 | Single-tenant and Multitenant |
| Washington DC | Washington DC 07 | Single-tenant and Multitenant |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="North America"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-northamerica}

## Resource pool
{: #tenant-plan-deploy-rp}

A resource pool combines compute, memory, and storage resources, and consist of one or more clusters. For more information, see [Adding resource pools](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

You can optionally enable SAP®-certified server profiles of either HANA and NetWeaver or NetWeaver.

## Profile storage type
{: #tenant-plan-deploy-storage}

For single-tenant Cloud Director sites, you can select NFS only storage or vSAN™ storage with optional NFS storage.

NFS only clusters do not have local flash storage and cannot be configured for vSAN.

vSAN storage with optional NFS storage is available for instances in locations with 25 GbE availability. vSAN clusters use bare metal host profiles with local flash storage and a RAID 6, FTT=2 policy. This policy is high-performance and high-resilience and requires at least seven hosts. vSAN clusters can also use NFS storage.

If you want to save storage space, you can enable vSAN deduplication and compression to reduce redundant data within each disk group. This option can increase overall storage space based on the data type.

The vSAN deduplication and compression option is available for enablement only when you order a single-tenant cluster.
{: note}

## Host profile
{: #tenant-plan-deploy-host}

{{site.data.keyword.cloud_notm}} offers several host profiles to choose from with different sizes and configurations of RAM and CPU. You can select the most optimized host profile to fit the target workloads. When you select a host profile, first assess the types of VMware VMs and workload you plan to run on {{site.data.keyword.vcf-aas}}.

* For migrating workloads into {{site.data.keyword.cloud_notm}}, open source tools such as [RVTools](https://www.robware.net/){: external} build an inventory of the existing VMWare environments. [RVTools](https://www.robware.net/) lists all VMs in an existing VMWare environment, including the VM CPU, RAM, and storage sizes.
* For new VMWare workloads, model out the applications and VM sizes (CPU, RAM, and storage) that you need for each VM.

After you have a list of target VMs including CPU, RAM, and storage requirements, next identify the largest and most important VM applications. When you select a host profile, you want to ensure to use the largest and most important applications to match against the host profile options. Match the largest VM's RAM requirements and CPU requirements against the list of host profiles. As a standard choice, use the host profile with at least as much physical RAM and CPU as the largest VM. It is also important to account for a 10 to 20 percent hypervisor overhead.

{{site.data.keyword.vcf-aas}} vCPU is mapped to physical cores at a ration of 2:1. For every one physical core, two vCPUs of compute are assigned.
{: note}

Lastly sum the total RAM, CPU, and storage requirements for all target VMs. The count of hosts multipled by CPU and RAM per host with a multiple of 20% hypervisor overhead provides you with the total number of hosts of the target profile that are required. Also, ensure to factor the size of VDC edges used in the VMware deployment into the total host count calculation.

### Bare metal server options
{: #tenant-plan-deploy-host-bms-req}

For single-tenant Cloud Director sites, you can select from various bare metal server CPU and memory sizes based on your selection of location and profile storage type.

| Profile | Sockets | Cores | RAM | vSAN usable capacity |
|:--------|:--------|:------|:----|:---------------------|
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 15 TB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 23 TB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 46 TB |
| Quad Intel 8260 Xeon | 4 | 96 | 1536 GB | 61 TB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB | 23 TB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB | 23 TB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB | 38 TB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB | 38 TB |
{: caption="Table 3. Available vSAN host profiles" caption-side="bottom"}
{: tab-title="vSAN clusters"}
{: tab-group="Host profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-vsan-hp}

| Profile | Sockets | Cores | RAM |
|:--------|:--------|:------|:----|
| Dual Intel 5218 Xeon | 2 | 32 | 192 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 384 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB |
| Quad Intel 8260 Xeon | 4 | 96 | 1536 GB |
| Dual Intel 5218 Xeon | 2 | 32 | 384 GB |
| Dual Intel 6248 Xeon | 2 | 40 | 384 GB |
| Dual Intel 5218 Xeon | 2 | 32 | 768 GB |
| Dual Intel 6248 Xeon | 2 | 40 | 768 GB |
{: caption="Table 4. Available NFS-only host profiles" caption-side="bottom"}
{: tab-title="NFS-only clusters"}
{: tab-group="Host profiles"}
{: class="simple-tab-table"}
{: #simpletabtable-nfs-hp}

## Performance characteristics
{: #tenant-plan-deploy-perf-char}

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

In-place consolidation of a fast-provisioned VM is not supported. As the number of linked clones grow, VM execution performance can be impacted.
{: important}

When you create your VDC and it is in **Available** status, you can enable or disable fast provisioning from the **Summary** tab on the VDC details page.

## Network settings
{: #tenant-plan-deploy-network}

For Cloud Director sites, you can select from public and private options for management and workload connectivity.

### Management connectivity
{: #tenant-plan-deploy-network-mgmt}

Management connectivity determines how you connect to the VMware Cloud Director UI or API and the Veeam® Backup and Replication service. You can access the management interfaces only from a source in the {{site.data.keyword.cloud_notm}} network. For private-only management network settings, you can create an ingress allowlist to allow connections from source subnets.

Select either public-only or private-only management connectivity.

### Workload connectivity
{: #tenant-plan-deploy-network-wkload}

Workload connectivity determines how you connect to your {{site.data.keyword.vcf-aas}} virtual machines (VMs) and vApps. Select either public and private or private-only workload connectivity.

When you select private-only workload connectivity for your Cloud Director site, all VDCs deployed in that site are private-only workloads. These VDCs do not have an incoming or outgoing connectivity path to the public internet and can access {{site.data.keyword.cloud_notm}} Services only over the private {{site.data.keyword.IBM_notm}} network.

You can connect VDCs to {{site.data.keyword.tg_full_notm}} to enable the workloads to securely connect to other workloads outside of the private network or are alternatively sandboxed in the VDC. For more information, see [Using Transit Gateway to interconnect {{site.data.keyword.vcf-aas}} with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections).

## Network edge type
{: #tenant-plan-deploy-edge}

VDCs connect to the public and IBM private networks through edges. Edges can also be used to connect multiple VDC networks together. You can create your VDC with or without a network edge. Network edge types include: Efficiency, Performance - M, Performance - L, and Performance - XL.

| Edge type | Details |
|:--------- |:------- |
| Efficiency | These edges allocate networking resources that can be used by up to 64 VDCs before another efficiency edge needs to be created. The first time an efficiency edge is selected new CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. Subsequent VDCs up to 64 can use this edge at no extra cost. This option is suitable for saving resources and costs with independent networking control per VDC. |
| Performance - M | This option is suitable when only L2 through L4 features such as NAT, routing, and L4 firewall are required and the total throughput requirement is in the range 2 - 6 Gbps. |
| Performance - L | This option is suitable when only L2 through L4 features such as NAT, routing, and L4 firewall are required and the total throughput is in the range 2 - 10 Gbps. This option is recommended for high traffic. |
| Performance - XL | This option provides the highest level of edge services and throughput over 10 Gbps. |
{: caption="Table 2. Network edge descriptions" caption-side="bottom"}

High inbound traffic from the public internet can trigger {{site.data.keyword.cloud_notm}}'s network protection platform. Contact IBM Support to discuss options for your network protection setting if you anticipate high inbound rates. For more information, see [Understanding network protection](/docs/subnets?topic=subnets-understanding-network-protect).
{: note}

### Network edge connection
{: #tenant-plan-deploy-edge-connection}

When you create your VDC with a network edge, you can select either a public and private network connection or a private-only network connection. If the Cloud Director site has a private-only connection, private-only is the only available option for the VDC network edge.

## Services for {{site.data.keyword.vcf-aas}}
{: #tenant-plan-deploy-services}

The following add-on services are optionally available for {{site.data.keyword.vcf-aas}} Cloud Director site instances.

### Veeam Backup and Replication
{: #tenant-plan-deploy-services-veeam}

For single-tenant instances, the Veeam Backup and Replication service is included by default with your Cloud Director site instance order. You can optionally remove the service before you create your instance. Service charges are incurred only if you choose to include the service in your order. You can add or remove the service later as required.

For multitenant instances, the Veeam Backup and Replication service is deployed on the Cloud Director site to provide VDCs with data recovery. If you want to use the service, you must install it after you create a multitenant VDC. Service charges are incurred only if you choose to install the service.

### VMware Cloud Director Availability
{: #tenant-plan-deploy-services-vcda}

Use the enterprise-level VMware Cloud Director Availability (VCDA) service to migrate VMs and vAPPS over a secure public internet connection.

The VCDA service is optionally included at no charge with your single-tenant Cloud Director site instance order. You can remove the service before you create your instance. You can add or remove the service later as required.

The VCDA service is included as a default option in multitenant VDC orders.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
