---

copyright:

  years: 2023, 2024

lastupdated: "2024-01-11"

keywords: add capacity, delete capacity, capacity adding, capacity remove, multitenant add capacity

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting capacity
{: #capacity-adding-deleting}

You can increase or decrease the reserved computing capacity for reserved *mutlitenant* virtual data centers and consumption limits for on-demand *multitenant* virtual data centers (VDCs).

vCPU and RAM charges for on-demand VDCs are based on the amount that is used for running workloads. To control cost, you can use limits to restrict the maximum amount of vCPU and RAM usage in the VDC.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab, then click a multitenant instance name.
3. On the consumption limit section of the **Summary** tab, click **Modify limit**.
4. Click the toggle switch to either disable or enable the limits.
5. For enabling consumption limits, enter the vCPU and RAM limits. Then, click **Save**.

## Related links
{: #capacity-adding-deleting-links}

* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting {{site.data.keyword.vmware-service_short}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
