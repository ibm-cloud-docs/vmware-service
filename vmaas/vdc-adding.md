---

copyright:

  years: 2022, 2025

lastupdated: "2025-03-10"

keywords: add virtual data center, virtual data center, add virtual data center, vdc add

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering virtual data center instances
{: #vdc-adding}

With {{site.data.keyword.vmware-service_full}}, you can quickly provision a complete VMware® by Broadcom virtual data center (VDC) environment and control the capacity that is used to run VMware workloads.

You can optionally deploy your VDC in a stretched regional compute high availability (HA) resource pool. To deploy your VDC in a regional compute HA resource pool, you must first create a stretched resource pool in your Cloud director site. For more information, see [Procedure to add stretch vSAN high availability resource pools to {{site.data.keyword.vcf-aas}} instances](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting#pvdc-adding-deleting-add-vsan-proc).

Regional network high availability is not currently supported. You cannot include a network edge in a highly available VDC.
{: restriction}

## Single-tenant virtual data centers
{: #vdc-adding-st}

For {{site.data.keyword.vcf-aas-full}} single-tenant VDCs, the minimum instance configuration consists of two hosts (2 Sockets - 32 Cores and 192 GB RAM). You can order up to 64 efficiency edges or one performance edge of medium size until more hosts are added to one of the clusters in the resource pool.

You can deploy VDCs only to an existing Cloud Director site. Therefore, you must create a single-tenant Cloud Director site before you can create a single-tenant VDC.

## Multitenant virtual data centers
{: #vdc-adding-mt}

For multitenant instances, you start by creating the multitenant VDC. A multitenant site is created automatically when you create the first multitenant VDC in a region. All multitenant VDCs that you create in a region are associated with the same site. 

For multitenant instances, the minimum instance configuration consists of one vCPU and 1 GB RAM.

## Resource group considerations
{: #vdc-adding-rg-reqs}

Even though you can place your {{site.data.keyword.vcf-aas}} VDCs into different resource groups, the resource group differentiation is useful only for billing purposes. For access control, IAM policies are tested against the Cloud Director site and not the VDCs.

For single-tenant VDCs, select the resource group for the Cloud Director site.

For multitenant VDCs, your Cloud Director site is placed in the same resource group as the first VDC in any region.

Because {{site.data.keyword.cloud_notm}} checks against the Cloud Director site resource group rather than the VDC resource group, users with permission to create a VDC can create one in any resource group.

When you use resource groups for IAM access, keep the Cloud Director site and all of the VDCs in the Cloud Director site in the same resource group.
{: tip}

## Billing details
{: #vdc-adding-billing}

| Feature         | Billing model      |
|:----------------|:-------------------|
| Multitenant \n **On-demand** vCPU | - vCPU is billed hourly. \n -  vCPU quantity is for all vCPU allocated to all running VMs in the VDC at any time per hour. \n - When a VM is stopped it is not counted in the total vCPU calculation. For example, if two running VMs both have 4 vCPU, then a third VM is started at 4 vCPU. The vCPU for the one hour period is 12 vCPU. |
| Multitenant \n **On-demand** RAM | - RAM is billed hourly. \n - RAM quantity is for all RAM allocated to all running VMs in the VDC at any given time per hour. \n -  When a VM is stopped it is not counted in the total RAM calculation. For example, if two running VMs have 16 GB RAM, then a third VM is started also at 16 GB RAM. The RAM for the one hour period is 48 GB. |
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

## Procedure to order a single-tenant VDC on a stretched resource pool
{: #vdc-adding-procedure-st-stretch}

Regional network high availability is not currently supported. You cannot include a network edge in a highly available VDC.
{: restriction}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Single-tenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Select a stretched resource pool.
      1. Toggle the **Regional compute high availability** switch on to display the available HA stretched resource pools. The toggle is disabled if stretched workload clusters are not available on the selected Cloud Director site.
      2. Expand the resource pool location and review the available regions and Cloud Director site options. Select a stretched resource pool.
      3. Optionally enable fast provisioning of virtual machines.
6. Review the included services, cost, accept the terms, and click **Create** to submit the VDC order.

## Procedure to order a single-tenant VDC on a nonstretched resource pool
{: #vdc-adding-procedure-st-nonstretch}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Single-tenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Ensure that the **Regional compute high availability** switch is off.
5. Expand the resource pool location and review the available regions and Cloud Director site options. Select a resource pool.
6. Optionally enable fast provisioning of virtual machines.
7. Review your options to create a network edge.
   * To order the VDC with a network edge, toggle the **Create with network edge** on and complete the following steps.
      1. Select the network connection for the edge. If the Cloud Director site is a private-only connection, the **Private only** option is required.
      2. Specify the edge type. Edge storage costs might occur.
   * To order the VDC without a network edge, toggle the **Create with network edge** switch off. This option is suitable for centralized networking administration and control over multiple VDCs.
6. Review the included services, cost, accept the terms, and click **Create** to submit the VDC order.

## Procedure to order a multitenant VDC on a stretched resource pool
{: #vdc-adding-procedure-mt-stretch}

Stretched resource pools are available only on some multitenant Cloud Director sites. Additional stretched resource pools will be made available over time.
{: note}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Multitenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Select a stretched resource pool.
      1. Toggle the **Regional compute high availability** switch on to display the available HA stretched resource pools. The toggle is disabled if stretched workload clusters are not available on the selected Cloud Director site. 

      2. Expand the resource pool location and review the available regions and Cloud Director site options. Select a stretched resource pool.
      3. Optionally enable fast provisioning of virtual machines.
6. Select the pricing plan according to your consumption needs.
7. Select resource allocations according to your pricing plan.
   * For on-demand, optionally enable consumption limits. Then, select the vCPU and RAM limits. Toggle the consumption limit option off if you do not want to set limits. Limits define the ceiling on the maximum amount of vCPU and RAM that can be used by the multitenant VDC.
   * For reserved, select the vCPU and RAM capacity reservation for the VDC. The CPU and RAM are reserved for exclusive use by the VDC and are metered monthly for the full reservation.
8. Review the cost, accept the terms, and click **Create** to submit the VDC order.

## Procedure to order a multitenant VDC on a nonstretched resource pool
{: #vdc-adding-procedure-mt-nonstretch}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. In the **{{site.data.keyword.vmware-service_short}}** page, select the **Multitenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Ensure that the **Regional compute high availability** switch is off.
5. Expand the resource pool location and review the available regions and Cloud Director site options. Select a resource pool.
6. Optionally enable fast provisioning of virtual machines.
7. Review your options to create a network edge.
   * To order the VDC with a network edge, toggle the **Create with network edge** on and complete the following steps.
      1. Select the network connection for the edge. If the Cloud Director site is a private-only connection, the **Private only** option is required.
      2. Specify the edge type. Edge storage costs might occur.
   * To order the VDC without a network edge, toggle the **Create with network edge** switch off. This option is suitable for centralized networking administration and control over multiple VDCs.
8. Select the pricing plan according to your consumption needs.
9. Select resource allocations according to your pricing plan.
   * For on-demand, optionally enable consumption limits. Then, select the vCPU and RAM limits. Toggle the consumption limit option off if you do not want to set limits. Limits define the ceiling on the maximum amount of vCPU and RAM that can be used by the multitenant VDC.
   * For reserved, select the vCPU and RAM capacity reservation for the VDC. The CPU and RAM are reserved for exclusive use by the VDC and are metered monthly for the full reservation.
10. Review the cost, accept the terms, and click **Create** to submit the VDC order.

For multitenant instances, install the Veeam service after you provision your VDC. For more information, see [Adding and deleting Veeam Backup](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting).
{: note}

## Results after you create virtual data centers
{: #vdc-adding-results}

* The deployment of the resources starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the VDC status.
* When all resources are successfully deployed, the ordered components are installed on your virtual platform.
* When the resources are ready to use, the status of the VDC is changed to **Available**.

## Related links
{: #vdc-adding-links}

* [Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
* [Managing Veeam for {{site.data.keyword.vcf-aas}} instances](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Managing resource groups](/docs/account?topic=account-rgs&interface=ui)
* [Managing IAM access for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui)
