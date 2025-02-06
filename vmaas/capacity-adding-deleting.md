---

copyright:

  years: 2023, 2025

lastupdated: "2025-02-04"

keywords: add capacity, delete capacity, capacity adding, capacity remove, multitenant add capacity

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting capacity
{: #capacity-adding-deleting}

You can increase or decrease the reserved computing capacity for reserved *mutlitenant* virtual data centers and consumption limits for on-demand *multitenant* virtual data centers (VDCs).

vCPU and RAM charges for on-demand VDCs are based on the amount that is used for running workloads. To control cost, you can use limits to restrict the maximum amount of vCPU and RAM usage in the VDC.

The capacity is set to the current utilization if the VDC utilization exceeds the requested capacity limit.
{: note}

## Procedure to add or delete capacity for {{site.data.keyword.vcf-aas}} VDCs
{: #capacity-adding-deleting-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab, then click an instance name.
3. In the consumption limit section of the **Summary** tab, click **Modify limit**.
4. Click the toggle switch to either turn limits on or off.
5. For enabling consumption limits, enter the vCPU and RAM limits. Then, click **Save**.

## Related links
{: #capacity-adding-deleting-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
