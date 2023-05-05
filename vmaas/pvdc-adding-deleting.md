---

copyright:

  years: 2022, 2023

lastupdated: "2023-04-27"

keywords: add provider vdc, delete provider vdc, pvdc add, pvdc remove, provider virtual data center

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting provider virtual data centers
{: #pvdc-adding-deleting}

You can scale an {{site.data.keyword.vmware-service_full}} instance in different ways. Scaling is used to size the instance properly, based on VMware® workload requirements. By creating a provider virtual data center (PVDC), you can increase the size of the {{site.data.keyword.vmware-service_short}} instance.

PVDCs are used within the {{site.data.keyword.vmware-service_short}} instance to form units of the following components, which are fully isolated between PVDCs:
* Compute
* Memory
* Storage

Each PVDC inherits the following policies from the {{site.data.keyword.vmware-service_short}} instance:
* Networking - Networking can be shared between PVDCs.
* User administration - Users and user policies that are configured for the {{site.data.keyword.vmware-service_short}} instance are shared across all PVDCs.
* Catalogs - Catalog images and policies also apply across all PVDCs in the instance.

PVDCs consist of one or more VMware vCenter Server® clusters. A new vCenter Server cluster is created as part of adding a PVDC to the {{site.data.keyword.vmware-service_short}} instance.

You can increase or decrease the capacity of your deployment by adding or deleting PVDCs to and from an instance. You can also expand capacity by adding more clusters to a PVDC.

Typically, the instance is scaled first through host count and storage count management within the cluster. Up to 25 homogeneous hosts are supported in a cluster. After the maximum size of 25 hosts for a cluster is reached, a new cluster is required.

VDCs deployed to a PVDC can use all compute, memory, and storage within the PVDC, including when multiple clusters exist. To get consistent workload performance, it's best if all clusters within the same PVDC use the same host profile type. VMware Cloud Director automatically selects and adjusts the placement of workload VMs across the clusters in the PVDC. Placement is not controlled by users with VMware Cloud Director.

A new PVDC is typically created for the following scenarios:
* Separate and isolate different types of VMware workloads. The previous guidance is to use the same host profile type for all clusters in the same PVDC. If different workloads are better suited for different host types, then separate PVDCs are required to ensure each workload runs on the correct host type.
* Run VM workload in different data centers within the region. All clusters in the same PVDC must be in the same data center. Regional high availability across data centers is achieved by creating PVDCs in separate data centers, and then deploying the virtual data center (VDC) and applications into each region. A load balancer is used to route requests to active instances of the target workload.

## Procedure to add PVDCs
{: #pvdc-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
3. Click **Add provider VDC +**.
4. On the **Add provider VDC** window, specify the settings for the new PVDC.
    1. Specify the PVDC name.
    2. Select the geography, region, and data center to host the new PVDC.
5. Click the **Host details** tab and specify the settings for the host.
    1. Specify the cluster name.
    2. Select the profile storage type.
    3. Select the host profile.
    4. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN™ storage, select a minimum of 6.
6. Click the **Attached NFS storage** tab and specify the settings for the storage.
7. Review the new cost, select the confirmation checkbox, and click **Order** to confirm.

When you deploy a new PVDC, a cluster is created. Cluster configuration can take up to 72 hours. After the cluster configuration is complete, you can perform user access and administration tasks.
{: note}

## Procedure to delete PVDCs
{: #pvdc-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
3. On the **Infrastructure** tab, locate the PVDC that you want to delete.
4. Click the vertical overflow menu next to the **Status** column for that cluster and click **Delete PVDC**.
5. Confirm that you want to delete the PVDC.

## Related links
{: #pvdc-adding-deleting-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
