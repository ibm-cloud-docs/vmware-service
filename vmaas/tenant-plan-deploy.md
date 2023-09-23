---

copyright:

  years:  2022, 2023

lastupdated: "2023-09-19"

keywords: ordering prerequisites, before you order, setup, environment setup

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Planning the deployment
{: #tenant-plan-deploy}

Before you order an {{site.data.keyword.vmware-service_full}} instance, ensure that you plan your deployment.

Consider the size of the VMware® deployment required. VMware deployments are sized based on the CPU, memory, and storage that are required to run the targeted workload. If you are planning a workload migration from on-premises to the cloud, the on-premises size is a good starting point. You can resize your VMware deployment at any time.

Review [VMware Cloud Director 10.4 Configuration Limits](https://configmax.esp.vmware.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.4&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director™.

## IBM Cloud data center availability
{: #tenant-plan-deploy-locations}

The following {{site.data.keyword.cloud_notm}} data centers are available for {{site.data.keyword.vmware-service_short}} deployment.

| Location | Data center |
|:----------|:----------|
| Frankfurt | Frankfurt 02 |
| Frankfurt | Frankfurt 04 |
| Frankfurt | Frankfurt 05 |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-eur}

| Location | Data center |
|:----------|:----------|
| Dallas | Dallas 10 |
| Dallas | Dallas 12 |
| Dallas | Dallas 13 |
| Washington DC | Washington DC 04 |
| Washington DC | Washington DC 06 |
| Washington DC | Washington DC 07 |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}
{: tab-title="North America"}
{: tab-group="Data centers for deployment"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-northamerica}

## SAP-certified server profiles
{: #tenant-plan-deploy-sap}

You can enable host options that have an SAP® IaaS certification for compatibility, supportability, and performance with SAP software applications.

SAP-certified server profiles include **HANA + NetWeaver** or **NetWeaver**.

SAP-certified provider virtual data centers support only NFS-only storage.
{: note}

## Profile storage type
{: #tenant-plan-deploy-storage}

You can select NFS-only storage or vSAN™ storage with optional NFS storage.

NFS-only clusters do not have local flash storage and cannot be configured for vSAN.

vSAN storage with optional NFS storage is available for instances in locations with 25 GbE availability. vSAN clusters use bare metal host profiles with local flash storage and a RAID 6, FTT=2 policy. This policy offers high-performance and high-resilience, and it requires at least 6 hosts. vSAN clusters can also use NFS storage.

If you want to save storage space, you can enable vSAN deduplication and compression to reduce redundant data within each disk group. This option can increase overall storage space based on the data type.

The vSAN deduplication and compression option is available for enablement only when you order a cluster.
{: note}

## Bare metal server profile
{: #tenant-plan-deploy-bms}

You can select from various bare metal server CPU and memory sizes based on your selection of location and profile storage type.

| CPU model | Sockets | Core | RAM |
|:----------|:----------|:----------|:----------|
| Dual Intel® Xeon® Platinum 8280M | 2 | 56 | 1536 GB |
| Dual Intel Xeon Platinum 8280M | 2 | 56 | 3072 GB |
| Dual Intel Xeon Platinum 8280M | 4 | 112 | 3072 GB |
| Dual Intel Xeon Platinum 8280M | 4 | 112 | 6144 GB |
{: caption="Table 2. SAP-certified profile configurations" caption-side="bottom"}
{: tab-title="HANA and NetWeaver"}
{: tab-group="SAP-certified configurations"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-hananetweaver}

| CPU model | Sockets | Core | RAM |
|:----------|:----------|:----------|:----------|
| Dual Intel Xeon Platinum 8280M | 2 | 56 | 1536 GB |
| Dual Intel Xeon Platinum 8280M | 2 | 56 | 3072 GB |
{: caption="Table 2. SAP-certified profile configurations" caption-side="bottom"}
{: tab-title="NetWeaver"}
{: tab-group="SAP-certified configurations"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-netweaver}

| CPU model | Sockets | Core | RAM |
|:----------|:----------|:----------|:----------|
| Dual Intel 5218 Xeon | 2 | 32 | 192 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 384 GB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB |
| Dual Intel 8260 Xeon | 4 | 96 | 1536 GB |
{: caption="Table 3. Host profile configurations" caption-side="bottom"}
{: tab-title="NFS-only configurations"}
{: tab-group="Host configurations"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-nfsonly}

| CPU model | Sockets | Core | RAM | vSAN usable capacity |
|:----------|:----------|:----------|:----------| :----------|
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 23 TB |
| Dual Intel 8260 Xeon | 2 | 48 | 768 GB | 46 TB |
{: caption="Table 3. Host profile configurations" caption-side="bottom"}
{: tab-title="vSAN and optional NFS storage"}
{: tab-group="Host configurations"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-vsannfs}

## Performance characteristics
{: #tenant-plan-deploy-perf-char}

Review the available storage performance tiers.

* 0.25 IOPS/GB; 24 TB increments
* 2 IOPS/GB; 24 TB increments
* 4 IOPS/GB; 24 TB increments
* 10 IOPS/GB; 4 TB increments

For NFS-only storage, you must select at least one unit of 2 IOPS/GB or higher.
{: requirement}

## Services for {{site.data.keyword.vmware-service_short}}
{: #tenant-plan-deploy-services}

The Veeam® Backup and Replication service is preinstalled and included by default for your instance order. You can remove the service from your instance order. Service charges are incurred only if you choose to include the service in your order.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
* [Managing Veeam for VMware as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam)
