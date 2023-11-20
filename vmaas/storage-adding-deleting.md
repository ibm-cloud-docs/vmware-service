---

copyright:

  years: 2022, 2023

lastupdated: "2023-11-10"

keywords: add storage, delete storage, storage adding, storage remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting storage
{: #storage-adding-deleting}

You can increase or decrease the NFS storage capacity of your *single-tenant* deployment by adding or deleting storage to and from a cluster.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click a single-tenant instance name.
3. Click the **Infrastructure** tab.
4. On the **Clusters** tab, click a cluster name to expand its details.
5. Click **Edit NFS storage**.
6. In the **Edit shared storage** window, increase or decrease the current sizings for the performance tiers available.
7. Review the new cost, select the confirmation checkbox, and click **Change** to confirm.

Editing the storage details might take up to 24 hours to complete. If a storage update is in progress, you cannot edit the storage until the previous operation is complete.
{: note}

## Related links
{: #storage-adding-deleting-links}

* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing and deleting {{site.data.keyword.vmware-service_short}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
