---

copyright:

  years: 2022, 2025

lastupdated: "2025-04-04"

keywords: add cluster, delete cluster, cluster adding, cluster remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting clusters
{: #cluster-adding-deleting}

You can add clusters to increase or delete clusters to decrease the capacity of your *single-tenant* instance deployment. VMware vCenter clusters are the building blocks of VMware Cloud Director resource pools and are added to existing resource pools or are added as part of a resource pool creation.

You can add a stretch vSAN™ high availability cluster only to a stretch vSAN high availability resource pool. NFS storage is not supported for high availability resource pools. For stretch vSAN clusters, the hosts are split into the first and second location of the resoure pool.

Some host profiles might not be available for a selected location. Contact your IBM Sales representative to request missing host profiles.
{: note}

## Procedure to add clusters to {{site.data.keyword.vcf-aas}} instances
{: #cluster-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab.
4. Locate the resource pool where you want to add the cluster and expand the cluster section. Then, click **Add cluster**.
5. In the **Add cluster** pane, specify the settings for the new cluster.
    1. Specify the cluster name.
    2. Select the host quantity.
       * For NFS-only storage, select a minimum of 2.
       * For vSAN + optional NFS storage, select a minimum of 7.
    3. Select the profile CPU type, then the profile storage type.
    4. Select the host profile.
    5. For vSAN, optionally enable vSAN de-duplication and compression.
    6. Review the cost, accept the terms, and click **Next**.
6. Specify the attached NFS storage settings.
7. Click **Order** to confirm.

## Procedure to add stretch vSAN high availability clusters to {{site.data.keyword.vcf-aas}} instances
{: #cluster-adding-deleting-add-vsan-proc}

Stretch vSAN high availability clusters support only Sapphire Rapids profiles.
{: requirement}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab.
4. Locate the stretched resource pool where you want to add the cluster and expand the cluster section. Then, click **Add cluster**.
5. In the **Add cluster** pane, specify the settings for the new cluster.
    1. Specify the cluster name.
    2. Select the host quantity. A minimum of 14 is required for stretch vSAN storage.
    3. Select the Sapphire Rapids host profile.
    4. Review the cost, accept the terms, and click **Order**.

## Before you delete clusters
{: #cluster-adding-deleting-before-delete}

Workload virtual machines (VMs) are deployed in virtual data centers (VDCs) that logically exist in the scope of a resource pool. Resource pools physically consist of one or more VMware vCenter clusters. When the resource pool contains multiple clusters and one cluster is deleted, all VMs running in that cluster are migrated to other clusters in the same resource pool.

VMs deployed to a specific storage performance tier are only migrated to the same performance tier of storage in the remaining clusters. You must ensure that the remaining clusters have compatible storage performance layers of the deleted cluster. The remaining clusters must also have enough CPU and memory to contain the VMs of the deleted cluster.

If not enough CPU, RAM, or equivalent storage performance for the cluster exists, the delete operation does not succeed. When the delete cluster operations are not successful, workloads are not impacted, and the operation is retried. Resource constraints are resolved by either stopping or deleting VMs or ensuring other clusters in the resource pool have the resources to support migrated workload VMs.

## Procedure to delete clusters from {{site.data.keyword.vcf-aas}} instances
{: #cluster-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab.
4. Expand **Clusters**, locate the cluster that you want to delete.
5. In the cluster row to delete, click **Actions** then **Delete**.
6. Confirm that you want to delete the cluster.

## Related links
{: #cluster-adding-deleting-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Adding resource pools](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
