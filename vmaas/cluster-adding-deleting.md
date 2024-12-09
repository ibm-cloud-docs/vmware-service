---

copyright:

  years: 2022, 2024

lastupdated: "2024-11-26"

keywords: add cluster, delete cluster, cluster adding, cluster remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting clusters
{: #cluster-adding-deleting}

You can add clusters to increase or delete clusters to decrease the capacity of your *single-tenant* instance deployment. VMware vCenter clusters are the building blocks of VMware Cloud Director resource pools and are added to existing resource pools or are added as part of a resource pool creation.

## Procedure to add clusters to {{site.data.keyword.vcf-aas}} instances
{: #cluster-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click a single-tenant instance name.
3. Click the **Resource pool** tab.
4. On the **Clusters** tab, click **Add cluster +**.
5. In the **Add cluster** pane, specify the settings for the new cluster.
    1. Specify the cluster name.
    2. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN™ storage, select a minimum of 7.
    3. Select the profile storage type.
    4. Select the host profile.
    5. Click **Next**.
6. Specify the attached NFS storage settings.
7. Review the new cost, select the confirmation checkbox, and click **Order** to confirm.

## Before you delete clusters
{: #cluster-adding-deleting-before-delete}

Workload virtual machines (VMs) are deployed in virtual data centers (VDCs) that logically exist in the scope of a resource pool. Resource pools physically consist of one or more VMware vCenter clusters. When the resource pool contains multiple clusters and one cluster is deleted, all VMs running in that cluster are migrated to other clusters in the same resource pool.

VMs deployed to a specific storage performance tier are only migrated to the same performance tier of storage in the remaining clusters. You must ensure that the remaining clusters have compatible storage performance layers of the deleted cluster. The remaining clusters must also have enough CPU and memory to contain the VMs of the deleted cluster.

If not enough CPU, RAM, or equivalent storage performance for the cluster exists, the delete operation does not succeed. When the delete cluster operations are not successful, workloads are not impacted, and the operation is retried. Resource constraints are resolved by either stopping or deleting VMs or ensuring other clusters in the resource pool have the resources to support migrated workload VMs.

## Procedure to delete clusters from {{site.data.keyword.vcf-aas}} instances
{: #cluster-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click a single-tenant instance name.
3. Click the **Resource pool** tab.
4. On the **Clusters** tab, locate the cluster that you want to delete.
5. Click the vertical overflow menu next to the **Status** column for that cluster and click **Delete cluster**.
6. Confirm that you want to delete.

## Related links
{: #cluster-adding-deleting-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
