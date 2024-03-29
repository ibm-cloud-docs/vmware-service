---

copyright:

  years: 2022, 2024

lastupdated: "2024-02-27"

keywords: add virtual data center, virtual data center, add virtual data center, vdc add

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering virtual data center instances
{: #vdc-adding}

With {{site.data.keyword.vmware-service_full}}, you can quickly provision a complete VMware® by Broadcom virtual data center (VDC) environment and control the capacity that is used to run VMware workloads.

For single-tenant VDCs, the minimum instance configuration consists of two hosts (2 Sockets - 32 Cores and 192 GB RAM). You can order up to 100 efficiency edges or one performance edge of medium size until more hosts are added to one of the clusters in the resource pool.

You can deploy VDCs only to an existing Cloud Director site. Therefore, you must create a single-tenant Cloud Director site before you can create a single-tenant VDC.
{: requirement}

For {{site.data.keyword.vmware-service_short}} multitenant, you start by creating the multitenant VDC. A {{site.data.keyword.vmware-service_short}} multitenant site is created automatically when you create the first multitenant VDC in a region. All multitenant VDCs that you create in a region are associated with the same site. User access to the multitenant VDCs within the Cloud account is controlled through IAM policies against the site. 

For multitenant instances, the minimum instance configuration consists of one vCPU and 1 GB RAM.

## Virtual data center name
{: #vdc-adding-vdc-name}

The VDC name is set to **vdc-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify a VDC name that meets the following requirements:
* The maximum length is 128 characters.
* Only alphanumeric, dash (-), and underscore (_) characters are allowed.
* The name must be unique within all active VDCs in your account. You can create a VDC that has the same name as a previously deleted VDC.

## Procedure to order {{site.data.keyword.vmware-service_short}} single-tenant virtual data centers
{: #vdc-adding-procedure-st}

1. In the VMware Solutions console, click **Create** on the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** page, select the **VMwaaS single-tenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
5. Select the region, Cloud Director instance, and resource pool. The instance and resource pool names are filtered based on the region setting.
6. Optionally toggle fast provisioning of virtual machines (VMs) on.
7. Review your options for a network edge:
   * To order a network edge, ensure that the toggle for **Create with network edge** is on and specify the edge type. Edge storage costs might occur.
   * To order without a network edge, toggle **Create with network edge** off. This option is suitable for centralized networking administration and control over multiple VDCs.
9. Review the included services, cost, accept the terms, and click **Create** to submit the VDC order.

## Procedure to order {{site.data.keyword.vmware-service_short}} multitenant virtual data centers
{: #vdc-adding-procedure-mt}

1. In the VMware Solutions console, click **Create** on the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** page, select the **VMwaaS multitenant Virtual data center** card.
3. Specify the VDC name and select the resource group.
4. Select the pricing plan according to your consumption needs.
5. Select the region of the Cloud Director site, the Cloud Director instance, and data center. The instance and data center names are filtered based on the region setting.
6. Optionally toggle fast provisioning of VMs on.
7. Review your options for a network edge:
   * To order a network edge, ensure that the toggle for **Create with network edge** is on and specify the edge type. Edge storage costs might occur.
   * To order without a network edge, toggle **Create with network edge** off. This option is suitable for centralized networking administration and control over multiple VDCs.
8. Select resource allocations according to your pricing plan.
   * For on-demand, optionally enable consumption limits. Then, select the vCPU and RAM limits. Toggle the consumption limit option off if you do not want to set limits. Limits define the ceiling on the maximum amount of vCPU and RAM that can be used by the multitenant VDC.
   * For reserved, select the vCPU and RAM capacity reservation for the VDC. The CPU and RAM are reserved for exclusive use by the VDC and are metered monthly for the full reservation.
9. Review the cost, accept the terms, and click **Create** to submit the VDC order.

For multitenant instances, install the Veeam service after you provision your VDC. For more information, see [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting).
{: note}

## Results after you create virtual data centers
{: #vdc-adding-results}

* The deployment of the resources starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the VDC status.
* When all resources are successfully deployed, the ordered components are installed on your virtual platform.
* When the resources are ready to use, the status of the VDC is changed to **Available**.

## Related links
{: #vdc-adding-links}

* [Viewing and deleting {{site.data.keyword.vmware-service_short}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
* [Viewing and deleting {{site.data.keyword.vmware-service_short}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
* [Managing Veeam for {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Managing IAM access for {{site.data.keyword.vmware-service_short}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui)
