---

copyright:

  years: 2023

lastupdated: "2023-11-15"

keywords: vmware as a service, price for vmware as a service, pricing plan, multitenant pricing

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vmware-service_short}} multitenant pricing
{: #mt_pricing}

{{site.data.keyword.vmware-service_full}} multitenant offers two pricing plans for creating VMware® virtual data centers (VDCs). VDCs incur charges for the following VDC resource usages:

* Storage allocations with tiered pricing based on storage performance
* Virtual CPU (vCPU) usage
* Virtual memory usage
* Egress on public networking
* Commercial operating system licenses used
* Third-party VMware services

| Plans | Description |
|:----- |:----------- |
| On-demand | - The vCPU and RAM VDCs are allocated based on the demand. Resources are not preallocated. If you have a large regional demand, delays in availability can occur.  \n  - The limits that are established for the amount of vCPU and RAM are maximums.  \n  - vCPU and RAM resource limits can be increased and decreased later as required.  \n  - The price is calculated hourly and it is based on the resource usage in the VDC.  \n  - The amount of storage that can be allocated and used in the VDC is unlimited. Charges are hourly based on GB of allocated storage.  \n  - The amount of inbound and outbound public networking is unlimited. Public outbound bandwidth is charged per GB. |
| Reserved | - The vCPU and RAM VDC reservations are pre-allocated and their availability is guaranteed.  \n  - vCPU and RAM resources can be increased and decreased later as required.  \n  - The amount of storage that can be allocated and used in the VDC is unlimited. Charges are hourly based on GB of allocated storage.  \n  - The amount of inbound and outbound public networking is unlimited. Public outbound bandwidth is charged per GB. |
{: caption="Table 1. Pricing plans" caption-side="bottom"}

## Price breakdown
{: #mt_pricing-cost}

### Usage
{: #mt_pricing-term-usage}

Metering is for the full potential size of the resource for the time period that the resource is used.

For example, a on-demand VDC is created with a resource limit of 100 vCPU and 800 GB RAM. The data center has no VMs running on it, so you do not receive a charge for the vCPU and RAM. If an 8 vCPU with 8 GB virtual machine (VM) is started, metering is calculated for the size of that VM. If the VM uses fewer resources than the ones assigned to it, metering is applicable to the full size of the VM.

### Allocation
{: #mt_pricing-term-alloc}

Metering is applicable to the full potential size of the resource for the life of the resource.

For example, a reserved VDC is created with a resource allocation of 100 vCPU and 800 GB RAM and no VMs are created or running on it. Metering is applicable to 100 vCPU and 800 GB RAM.

### Monthly peak metric usage
{: #mt_pricing-term-mon-peak}

The maximum value of the metric used over a full month.

For example, a reserved VDC is created with 100 vCPU and 800 GB RAM. Later in the month, the data center is reduced to 50 vCPU and 400 GB RAM. The monthly peak usage is 100 vCPU and 800 GB RAM.

### Hourly peak metric usage
{: #mt_pricing-term-hour-peak}

The maximum value of the metric used over an hour. For example, if 100 vCPU is used for a minute of the hour with 0 vCPU used for the other 59 mins, the hourly peak metric usage is 100 vCPU.


## {{site.data.keyword.vmware-service_short}} On-demand billing plan
{: #mt_pricing-cost-ondemand}

{{site.data.keyword.vmware-service_short}} on-demand VDC resources are allocated as needed. Pricing is hourly based on the resource usage in the VDC. The following metrics are part of this plan.

Storage policy availability can vary by region and deployment topology. On the {{site.data.keyword.vmware-service_short}} order page, select the **About** tab to view available storage policy offerings.
{: note}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:----------|:------------|
| MAX_BASE_COST | Monthly | VDC price, which includes the edge gateway with five IP addresses. |
| TOTAL_VCPU_HOURS | Hourly | The peak vCPU **usage** over the period of an hour. |
| TOTAL_RAM_GB_HOURS | Hourly | The peak memory **usage** over the period of an hour. |
| TOTAL_EGRESS_GB | Usage | The **total** outbound public traffic is charged per GB transferred over the period of an hour. This value includes public outbound traffic. |
{: class="simple-tab-table"}
{: caption="Table 2. On-demand billing plan - General metrics" caption-side="bottom"}
{: #table1}
{: tab-title="General metrics"}
{: tab-group="on-demand-metrics"}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:----------|:------------|
| TOTAL_STORAGE_STANDARD_GB_HOURS | Hourly | The standard storage policy pricing is the same as the 4-IOPS/GB storage policy. The number of IOPS/GB for the standard storage policy is not guaranteed. |
| TOTAL_STORAGE_POINT_TWO_FIVE_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 0.25 IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_TWO_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 2-IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_FOUR_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 4-IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_TEN_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 10 IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_VSAN_GB_HOURS | Hourly | The peak storage **allocation** over the period of an hour. |
| STORAGE_EDGE_EFFICIENCY | Monthly | Allocate networking resources used by up to 100 VDCs before another efficiency edge needs to be created. |
| STORAGE_EDGE_MEDIUM | Monthly | Use when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput requirement is less than 2 Gbps. |
| STORAGE_EDGE_LARGE | Monthly | Use when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput is in the range 2 - 10 Gbps.|
| STORAGE_EDGE_EXTRA_LARGE | Monthly | Use when the total throughput required for multiple Gbps for L7 and VPN. |
{: caption="Table 2. On-demand billing plan - Storage metrics" caption-side="bottom"}
{: #table2}
{: tab-title="Storage metrics"}
{: tab-group="on-demand-metrics"}
{: class="simple-tab-table"}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:------------|:------------|
| TOTAL_WINDOWS_LICENSE_HOURS | Hourly | The peak number of Windows® license **usage** based on Windows VM vCPU size. For example, if you have two Windows VMs, one VM with 16 vCPU and one VM with 8 vCPU, the usage is 24 vCPU of Windows license usage. |
| TOTAL_RHEL_SMALL_LICENSES | Hourly | The peak (High Watermark) number of small RHEL licenses usage in 1-hour intervals. Small RHEL VMs are four cores or smaller. |
| TOTAL_RHEL_LARGE_LICENSES | Hourly | The peak (High Watermark) number of large RHEL licenses usage in 1-hour intervals. Large RHEL VMs are larger than four cores. |
{: caption="Table 2. On-demand billing plan - Operating system metrics" caption-side="bottom"}
{: #table3}
{: tab-title="Operating system metrics"}
{: tab-group="on-demand-metrics"}
{: class="simple-tab-table"}

## {{site.data.keyword.vmware-service_short}} Reserved billing plan
{: #mt_pricing-cost-reserved}

{{site.data.keyword.vmware-service_short}} reserved VDC resources are preallocated and guaranteed. Pricing is monthly based on the allocation size of the VDC.

Storage policy availability can vary by region and deployment topology. On the VMware Shared order page, select the **About** tab to view available storage policy offerings.
{: note}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:----------|:------------|
| MAX_VCPU | Monthly | The peak vCPU **allocation** for the VDC over the period of one month. The peak vCPU metric is determined by the largest vCPU reservation value that is selected by the customer over a one month period. |
| MAX_RAM_GB | Monthly | The peak memory **allocation** for the VDC over the period of one month. The peak vCPU metric is determined by the largest memory reservation value that is selected by the customer over a one month period. |
| TOTAL_EGRESS_GB  | Usage | The **total** outbound public traffic is charged per GB transferred over the period of one month. This value includes the outbound traffic through the VDC NSX edge to the public internet. |
{: class="simple-tab-table"}
{: caption="Table 3. Reserved billing plan - General metrics" caption-side="bottom"}
{: #reservedbilling-table1}
{: tab-title="General metrics"}
{: tab-group="res-billing-metrics"}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:----------|:------------|
| TOTAL_STORAGE_STANDARD_GB_HOURS | Hourly | The standard storage policy pricing is the same as the 4-IOPS/GB storage policy. The number of IOPS/GB for the standard storage policy is not guaranteed. |
| TOTAL_STORAGE_POINT_TWO_FIVE_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 0.25 IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_TWO_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 2-IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_FOUR_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 4-IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_TEN_IOPS_GB_HOURS | Hourly | The peak storage **allocation** at the 10 IOPS/GB tier over the period of an hour. |
| TOTAL_STORAGE_VSAN_GB_HOURS | Hourly | The peak storage **allocation** over the period of an hour. |
| STORAGE_EDGE_EFFICIENCY | Monthly | Allocate networking resources used by up to 100 VDCs before another efficiency edge needs to be created. |
| STORAGE_EDGE_MEDIUM | Monthly | Use when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput requirement is less than 2 Gbps. |
| STORAGE_EDGE_LARGE | Monthly | Use when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput is in the range 2 - 10 Gbps.|
| STORAGE_EDGE_EXTRA_LARGE | Monthly | Use when the total throughput required for multiple Gbps for L7 and VPN. |
{: caption="Table 3. Reserved billing plan - Storage metrics" caption-side="bottom"}
{: #reservedbilling-table2}
{: tab-title="Storage metrics"}
{: tab-group="res-billing-metrics"}
{: class="simple-tab-table"}

| Metric                                   | Frequency | Description |
|:-----------------------------------------|:------------|:------------|
| TOTAL_WINDOWS_LICENSE_HOURS | Hourly | The peak number of Windows® license **usage** based on Windows VM vCPU size. For example, if you have two Windows VMs, one VM with 16 vCPU and one VM with 8 vCPU, the usage is 24 vCPU of Windows license usage. |
| TOTAL_RHEL_SMALL_LICENSES | Hourly | The peak (High Watermark) number of small RHEL licenses usage in 1-hour intervals. Small RHEL VMs are four cores or smaller. |
| TOTAL_RHEL_LARGE_LICENSES | Hourly | The peak (High Watermark) number of large RHEL licenses usage in 1-hour intervals. Large RHEL VMs are larger than four cores. |
{: caption="Table 3. Reserved billing plan - Operating system metrics" caption-side="bottom"}
{: #reservedbilling-table3}
{: tab-title="Operating system metrics"}
{: tab-group="res-billing-metrics"}
{: class="simple-tab-table"}

## Licenses and fees for Veeam Backup and Replication
{: #mt_pricing-services}

Veeam® Backup and Replication usage incurs the following on-demand charges. You can view the charges on the **Billing and usage** view along with the usage and charges from all other {{site.data.keyword.cloud_notm}} services.

In the **Usage summary** view, locate the **VMware as a Service** service type. Locate the **Organization** plan to find the Veeam usage across all VDCs in that organization. The VDC usage is located in a separate plan for either {{site.data.keyword.vmware-service_short}} on-demand or {{site.data.keyword.vmware-service_short}} reserved.

For more information about Licenses and fees for Veeam Backup and Replication for {{site.data.keyword.vmware-service_short}} single-tenant, see [VMware as a Service single-tenant pricing](/docs/vmware-service?topic=vmware-service-st_pricing).
{: note}

| Metric                                   | Frequency   | Description |
|:-----------------------------------------|:------------|:------------|
| ORG_VEEAM_LICENSES | Monthly | Veeam license charge for every VM under backup. The monthly charge is for the highest number of VMs under backup at any time period in the month. |
| ORG_VEEAM_BLOCK_STORAGE | Hourly | Charge per GB of block storage used for all backups. |
| ORG_VEEAM_OBJECT_STORAGE | Hourly | Charge per GB of object storage used for all backups. |
{: caption="Table 4. Licenses and fees for Veeam on multitenant" caption-side="bottom"}

For the Veeam service, all backups go to both the block storage cross data center and to Cloud Object Storage.

No additional Veeam usage charges for {{site.data.keyword.vmware-service_short}} are incurred.
{: note}

## Related links
{: #mt_pricing-related}

* [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [VMware as a Service single-tenant pricing](/docs/vmware-service?topic=vmware-service-st_pricing)
* [VMware Cloud Director](https://docs.vmware.com/en/VMware-Cloud-Director/10.4/VMware-Cloud-Director-Tenant-Portal-Guide/GUID-74C9E10D-9197-43B0-B469-126FFBCB5121.html){: external}
