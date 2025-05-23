---

copyright:

  years: 2022, 2025

lastupdated: "2025-05-20"

keywords: add resource pool, delete resource pool, resource pool

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding resource pools
{: #pvdc-adding-deleting}

You can scale an {{site.data.keyword.vmware-service_full}} *single-tenant* instance in different ways. Scaling is used to size the instance properly, based on VMware® by Broadcom workload requirements. By creating a resource pool, you can increase the size of the {{site.data.keyword.vcf-aas-full}} instance.

A resource pool is a boundary of compute, storage, and network resources for hosting virtual data centers (VDCs) to run workloads. VDCs created against a resource pool are bound to use the infrastructure from that resource pool.

Resource pools are used within the {{site.data.keyword.vcf-aas}} instance to form units of compute, memory, and storage components. These resources are fully isolated between resource pools.

Each resource pool inherits the following policies from the {{site.data.keyword.vcf-aas}} instance:
* Networking - Networking can be shared between resource pools.
* User administration - Users and user policies that are configured for the {{site.data.keyword.vcf-aas}} instance are shared across all resource pools.
* Catalogs - Catalog images and policies also apply across all resource pools in the instance.

You can optionally create a resource pool to stretch the workload cluster across two different data centers within a multizone region. A stretched vSAN™ high availability (HA) resource pool helps to protect critical workloads by increasing the availability of the VMware by Broadcom infrastructure.

Highly available resource pools are supported on a Cloud Director site region only when a Sapphire Rapids server is available. HA resource pools require stretched clusters with vSAN storage profiles. NFS storage is not supported.
{: requirement}

Resource pools consist of one or more VMware vCenter Server® clusters. A new vCenter Server cluster is created when you add a resource pool to the {{site.data.keyword.vcf-aas}} instance.

You can increase or decrease the capacity of your deployment by adding or deleting resource pools to and from an instance. You can also expand capacity by adding more clusters to a resource pool.

Typically, the instance is scaled first through the host count and the storage count management within the cluster. Up to 25 homogeneous hosts are supported in a cluster. After the maximum size of 25 hosts for a cluster is reached, a new cluster is required. For stretched vSAN high availability clusters, the hosts are split into the first and second location of the resource pool. The minimum host requirement for stretched vSAN high availability clusters is 14.

VDCs deployed to a resource pool can use all compute, memory, and storage within the resource pool, including when multiple clusters exist. To get consistent workload performance, it's best if all clusters within the same resource pool use the same host profile type. VMware Cloud Director automatically selects and adjusts the placement of workload VMs across the clusters in the resource pool. Placement is not controlled by users with VMware Cloud Director.

A new resource pool is typically created for the following scenarios:
* Separate and isolate different types of VMware by Broadcom workloads. The previous guidance is to use the same host profile type for all clusters in the same resource pool. If different workloads are better suited for different host types, then separate resource pools are required to ensure each workload runs on the correct host type.
* Run VM workload in different data centers within the region. All clusters in the same resource pool must be in the same data center. Regional high availability across data centers is achieved by creating resource pools in separate data centers, and then deploying the VDC and applications into each region. A load balancer is used to route requests to active instances of the target workload.

When you deploy a new resource pool, a cluster is created. Cluster configuration can take up to 72 hours. After the cluster configuration is complete, you can complete user access and administration tasks.
{: note}

## Procedure to add resource pools to {{site.data.keyword.vcf-aas}} instances
{: #pvdc-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab, then click **Add resource pool**.
4. In the **Add resource pool** pane, specify the settings for the new resource pool.
   1. Specify the resource pool name.
   2. Optionally enable SAP®-certified server profiles and select the profile type.
   3. Select the resource pool location.
   4. Review the cost, accept the terms, and click **Next**.
5. Specify the host details.
   1. Specify the cluster name.
   2. Select the host quantity.
      * For NFS-only storage, select a minimum of 2.
      * For vSAN + optional NFS storage, select a minimum of 7.
   3. Select the profile storage type.
   4. Select the host profile.
   5. For vSAN, optionally enable vSAN de-duplication and compression.
   6. Click **Next**.
6. Specify the attached NFS storage settings.
7. Click **Order** to confirm.

## Procedure to add stretched vSAN high availability resource pools to {{site.data.keyword.vcf-aas}} instances
{: #pvdc-adding-deleting-add-vsan-proc}

Stretched vSAN high availability clusters support only Sapphire Rapids profiles.
{: requirement}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab, then click **Add resource pool**.
4. In the **Add resource pool** pane, specify the settings for the new resource pool.
    1. Enable **High availability resource pool** to stretch the workload cluster across multiple data centers within a region. 
    2. Specify the resource pool name.
    3. Select the resource pool locations.
    4. Click **Next**.
5. Specify the host details.
    1. Specify the cluster name.
    2. Select the host quantity. A minimum of 14 is required for stretched vSAN storage.
    3. Select the host profile.
    4. Optionally enable vSAN de-duplication and compression.
6. Review the cost, accept the terms, and click **Order** to confirm.

## Procedure to delete a resource pool
{: #pvdc-adding-deleting-delete-proc}

A resource pool is deleted when the last cluster on the resource pool is deleted. For more information about deleting clusters, see [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting).

## Related links
{: #pvdc-adding-deleting-links}

* [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
