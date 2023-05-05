---

copyright:

  years:  2022, 2023

lastupdated: "2023-05-05"

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

## Profile storage type
{: #tenant-plan-deploy-storage}

You can select NFS only storage or vSAN™ storage with optional NFS storage.

NFS only clusters do not have local flash storage and cannot be configured for vSAN.

vSAN storage with optional NFS storage is available for instances in locations with 25 GbE availability. vSAN clusters use bare metal host profiles with local flash storage and a RAID 6, FTT=2 policy. This is a high-performance and high-resilience policy, and it requires at least 6 hosts. vSAN clusters can also use NFS storage.

If you want to save storage space, you can enable vSAN deduplication and compression to reduce redundant data within each disk group. This option can increase overall storage space based on the data type.

The vSAN deduplication and compression option is available for enablement only when you order a cluster.
{: note}

## Bare metal server requirements
{: #tenant-plan-deploy-bms-req}

You can select from various bare metal server CPU and memory sizes based on your selction of location and profile storage type.

For vSAN cluters, you can select Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 768 GB RAM) with either 15 TB, 23 TB, or 30 TB of vSAN usable capacity.

The following options are available for NFS only clusters.

* Dual Intel® 5218 Xeon® (2 Sockets - 32 Cores, 192 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 384 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 768 GB RAM)
* Dual Intel 8260 Xeon (4 Sockets - 96 Cores, 1536 GB RAM)

## Performance characteristics
{: #tenant-plan-deploy-perf-char}

Review the available storage performance tiers.

* 0.25 IOPS/GB
* 2 IOPS/GB
* 4 IOPS/GB
* 10 IOPS/GB

For NFS only storage, you must select at least one unit of 2 IOPS/GB or higher.
{: requirement}

## Configuration limits for VMware Cloud Director
{: #tenant-plan-deploy-cloud-dir-limits}

Review [VMware Cloud Director 10.4 Configuration Limits](https://configmax.esp.vmware.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.4&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director™.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
