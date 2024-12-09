---

copyright:

  years: 2022, 2024

lastupdated: "2024-05-23"

keywords: add resource pool, delete resource pool, resource pool

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding resource pools
{: #pvdc-adding-deleting}

You can scale an {{site.data.keyword.vmware-service_full}} *single-tenant* instance in different ways. Scaling is used to size the instance properly, based on VMware® by Broadcom workload requirements. By creating a resource pool, you can increase the size of the {{site.data.keyword.vcf-aas-full}} instance.

A resource pool is a boundary of compute, storage, and network resources for hosting virtual data centers (VDCs) to run workloads. VDCs created against a resource pool are bound to use the infrastructure from that resource pool.

Resource pools are used within the {{site.data.keyword.vcf-aas}} instance to form units of the following components, which are fully isolated between resource pools:
* Compute
* Memory
* Storage

Each resource pool inherits the following policies from the {{site.data.keyword.vcf-aas}} instance:
* Networking - Networking can be shared between resource pools.
* User administration - Users and user policies that are configured for the {{site.data.keyword.vcf-aas}} instance are shared across all resource pools.
* Catalogs - Catalog images and policies also apply across all resource pools in the instance.

Resource pools consist of one or more VMware vCenter Server® clusters. A new vCenter Server cluster is created as part of adding a resource pool to the {{site.data.keyword.vcf-aas}} instance.

You can increase or decrease the capacity of your deployment by adding or deleting resource pools to and from an instance. You can also expand capacity by adding more clusters to a resource pool.

Typically, the instance is scaled first through host count and storage count management within the cluster. Up to 25 homogeneous hosts are supported in a cluster. After the maximum size of 25 hosts for a cluster is reached, a new cluster is required.

VDCs deployed to a resource pool can use all compute, memory, and storage within the resource pool, including when multiple clusters exist. To get consistent workload performance, it's best if all clusters within the same resource pool use the same host profile type. VMware Cloud Director automatically selects and adjusts the placement of workload VMs across the clusters in the resource pool. Placement is not controlled by users with VMware Cloud Director.

A new resource pool is typically created for the following scenarios:
* Separate and isolate different types of VMware workloads. The previous guidance is to use the same host profile type for all clusters in the same resource pool. If different workloads are better suited for different host types, then separate resource pools are required to ensure each workload runs on the correct host type.
* Run VM workload in different data centers within the region. All clusters in the same resource pool must be in the same data center. Regional high availability across data centers is achieved by creating resource pools in separate data centers, and then deploying the VDC and applications into each region. A load balancer is used to route requests to active instances of the target workload.

A resource pool is deleted when the last VDC on the resource pool is deleted.
{: note}

## Procedure to add resource pools to {{site.data.keyword.vcf-aas}} instances
{: #pvdc-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click a single-tenant instance name.
3. Click the **Resource pool** tab, then click **Add resource pool**.
4. In the **Add resource pool** panel, specify the settings for the new resource pool.
    1. Specify the resource pool name.
    2. Optionally enable SAP®-certified server profiles and select the profile type.
    3. Select the resource pool location.
    4. Click **Next**.
5. Specify the host details.
    1. Specify the cluster name.
    2. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN™ storage, select a minimum of 7.
    3. Select the profile storage type.
    4. Select the host profile.
    5. Click **Next**.
6. Specify the attached NFS storage settings.
7. Review the new cost, select the confirmation checkbox, and click **Order** to confirm.

When you deploy a new resource pool, a cluster is created. Cluster configuration can take up to 72 hours. After the cluster configuration is complete, you can perform user access and administration tasks.
{: note}

## Related links
{: #pvdc-adding-deleting-links}

* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
