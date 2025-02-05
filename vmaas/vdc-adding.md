---

copyright:

  years: 2022, 2025

lastupdated: "2025-02-04"

keywords: add virtual data center, virtual data center, add virtual data center, vdc add

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering virtual data center instances
{: #vdc-adding}

With {{site.data.keyword.vmware-service_full}}, you can quickly provision a complete VMware® by Broadcom virtual data center (VDC) environment and control the capacity that is used to run VMware workloads.

For single-tenant VDCs, the minimum instance configuration consists of two hosts (2 Sockets - 32 Cores and 192 GB RAM). You can order up to 64 efficiency edges or one performance edge of medium size until more hosts are added to one of the clusters in the resource pool.

You can deploy VDCs only to an existing Cloud Director site. Therefore, you must create a single-tenant Cloud Director site before you can create a single-tenant VDC.
{: requirement}

For {{site.data.keyword.vcf-aas-full}} multitenant, you start by creating the multitenant VDC. A {{site.data.keyword.vcf-aas}} multitenant site is created automatically when you create the first multitenant VDC in a region. All multitenant VDCs that you create in a region are associated with the same site. User access to the multitenant VDCs within the Cloud account is controlled through IAM policies against the site. 

For multitenant instances, the minimum instance configuration consists of one vCPU and 1 GB RAM.

## Billing details
{: #vdc-adding-billing}

| Feature         | Billing model      |
|:----------------|:-------------------|
| Multitenant \n **On-demand** vCPU | - vCPU is billed hourly. \n -  vCPU quantity is for all vCPU allocated to all running VMs in the VDC at any time per hour. \n - When a VM is stopped it is not counted in the total vCPU calculation. For example, if two running VMs both have 4 vCPU, then a third VM is started at 4 vCPU. The vCPU for the one hour period is 12 vCPU. |
| Multitenant \n **On-demand** RAM | - RAM is billed hourly. \n - RAM quantity is for all RAM allocated to all running VMs in the VDC at any given time per hour. \n -  When a VM is stopped it is not counted in the total RAM calculation. For example, if there are two running VMs that both have 16 GB RAM, then a third VM is started also at 16 GB RAM. The RAM for that one hour period is 48 GB. |
| Multitenant \n **Reserved** vCPU   | - vCPU is billed monthly for the highest capacity reservation set for that month. \n - VDC reservations are prorated for the first month. If the reservation is increased, then decreased again, the high water mark vCPU capacity reservation is charged for that month. |
| Multitenant \n **Reserved** RAM | - RAM is billed monthly for the highest capacity reservation set for that month. \n - VDC reservations are prorated for the first month. If the reservation is increased, then decreased again, the high water mark RAM capacity reservation is charged for that month. |
| Multitenant shared storage | - Shared storage is billed hourly. \n - Storage quantity includes all storage that is allocated per VM, even if the VM is stopped, and all VM snapshots. \n - Storage usage increases with new VMs and snapshots and decreases when VMs and snapshots are removed. |
| Multitenant edges | - Edges are billed monthly based on the type of edge used. The efficiency edge is the most cost-effective edge and the extra large edge provides the highest level of edge services and throughput over 10 Gbps. \n - Edges are prorated for the first month. \n - Each edge change is treated individually. For example, when you remove an edge then add an edge, the bill reflects both edges for that month. |
{: caption="Billing details" caption-side="bottom"}

## Name requirements
{: #vdc-adding-vdc-name}

The VDC name is set to **vdc-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify a VDC name that meets the following requirements:
* The maximum length is 128 characters.
* Only alphanumeric, dash (-), and underscore (_) characters are allowed.
* The name must be unique within all active VDCs in your account. You can create a VDC that has the same name as a previously deleted VDC.

## Procedure to order {{site.data.keyword.vcf-aas}} single-tenant virtual data centers
{: #vdc-adding-procedure-st}

When you use resource groups for IAM access, you must keep the Cloud Director site and all of the VDCs in the Cloud Director site in the same resource group.
{: requirement}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Single-tenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Specify how you would like the VDC deployed.
4. Select the region, Cloud Director instance, and resource pool. The instance and resource pool names are filtered based on the region setting.
5. Optionally enable fast provisioning of virtual machines (VMs).Review your options for a network edge.
   * To order a network edge, ensure that the toggle for **Create with network edge** is on and complete the following steps.
      1. Select the network connection for the edge. If the Cloud Director site is a private-only connection, the **Private only** option is available.
      2. Specify the edge type. Edge storage costs might occur.
   * To order without a network edge, turn off **Create with network edge**. This option is suitable for centralized networking administration and control over multiple VDCs.
7. Review the included services, cost, accept the terms, and click **Create** to submit the VDC order.

## Procedure to order {{site.data.keyword.vcf-aas}} multitenant virtual data centers
{: #vdc-adding-procedure-mt}

When you use resource groups for IAM access, you must keep the Cloud Director site and all of the VDCs in the Cloud Director site in the same resource group.
{: requirement}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Multitenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Specify how you would like the VDC deployed.
4. Select the region of the Cloud Director site, the Cloud Director instance, and data center. The instance and data center names are filtered based on the region setting.
5. Optionally enable fast provisioning of VMs.
6.  Review your options for a network edge:
   * To order a network edge, ensure that the toggle for **Create with network edge** is on and complete the following steps.
      1. Select the network connection for the edge. If the Cloud Director site is a private-only connection, the **Private only** option is available.
      2. Specify the edge type. Edge storage costs might occur.
   * To order without a network edge, turn off **Create with network edge**. This option is suitable for centralized networking administration and control over multiple VDCs.
7. Select the pricing plan according to your consumption needs.
8. Select resource allocations according to your pricing plan.
   * For on-demand, optionally enable consumption limits. Then, select the vCPU and RAM limits. Toggle the consumption limit option off if you do not want to set limits. Limits define the ceiling on the maximum amount of vCPU and RAM that can be used by the multitenant VDC.
   * For reserved, select the vCPU and RAM capacity reservation for the VDC. The CPU and RAM are reserved for exclusive use by the VDC and are metered monthly for the full reservation.
9. Review the cost, accept the terms, and click **Create** to submit the VDC order.

For multitenant instances, install the Veeam service after you provision your VDC. For more information, see [Adding and deleting Veeam Backup](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting).
{: note}

## Results after you create virtual data centers
{: #vdc-adding-results}

* The deployment of the resources starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the VDC status.
* When all resources are successfully deployed, the ordered components are installed on your virtual platform.
* When the resources are ready to use, the status of the VDC is changed to **Available**.

## Related links
{: #vdc-adding-links}

* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
* [Managing Veeam for {{site.data.keyword.vcf-aas}} instances](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Managing IAM access for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui)
