---

copyright:

  years:  2022, 2023

lastupdated: "2023-01-24"

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

## Performance characteristics
{: #tenant-plan-deploy-perf-char}

Consider the performance characteristics and review the available storage performance tiers:

* 0.25 IOPS/GB
* 2 IOPS/GB
* 4 IOPS/GB
* 10 IOPS/GB

## Bare metal server requirements
{: #tenant-plan-deploy-bms-req}

Consider the bare metal servers requirements.

You can select from various CPU and memory sizes based on the selected location.

* Dual Intel® 5218 Xeon® (2 Sockets - 32 Cores, 192 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 384 GB RAM)
* Dual Intel 8260 Xeon (2 Sockets - 48 Cores, 768 GB RAM)
* Dual Intel 8260 Xeon (4 Sockets - 96 Cores, 1536 GB RAM)

## Configuration limits for VMware Cloud Director
{: #tenant-plan-deploy-cloud-dir-limits}

Review [VMware Cloud Director 10.4 Configuration Limits](https://configmax.esp.vmware.com/guest?vmwareproduct=%20VMware%20Cloud%20Director&release=VMware%20Cloud%20Director%2010.4&categories=35-0){: external} to ensure that you understand configuration limits in VMware Cloud Director.

## Related links
{: #tenant-plan-deploy-links}

* [FAQ](/docs/vmware-service?topic=vmware-service-faq-general)
