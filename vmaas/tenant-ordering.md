---

copyright:

  years: 2022, 2023

lastupdated: "2023-07-06"

keywords: order tenant instance, single tenant instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering}

You can order an {{site.data.keyword.vmware-service_full}} instance from the VMware Solutions user interface after you review the minimum requirements.

## Minimum requirements for {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering-min-req}

Minimum 2 servers (6 servers for vSAN profiles)
 * 2 hosts (2-socket 32 cores, 192 GB RAM)
 * 24 TB of shared storage
 * Minimum of 1 virtual data center (VDC) with a medium performance edge

You can start with just one virtual data center (VDC) and a performance network edge of medium size.

## Procedure to order {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering-procedure}

1. In the VMware Solutions console, click **Create** on the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the **VMwaaS single-tenant Cloud Director site** card.
3. Specify the Cloud Director site name and select a resource group.

   If **No resource group available** is displayed, you currently do not have the permission to add VDCs to any resource group in this account. Contact the account owner to be assigned the **Editor** or **Administrator** role on a resource group in the account. For more information, see [IAM roles](/docs/account?topic=account-userroles).
4. Select the Cloud Director geography and location.
5. Specify the provider virtual data center (PVDC) name and select PVDC location.
6. Specify the settings for the cluster.
    1. Specify the cluster name.
    2. Select the profile storage type.
    3. Select the host profile.
    4. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN™ storage, select a minimum of 6.
    5. For vSAN, optionally select the **Enable vSAN de-duplication & compression** checkbox to save storage space.
    6. Select the sizings for one or more IOPS/GB performance tiers for attached NFS storage.
7. Review the add-on service option to deploy the Veeam® Backup and Replication service. Toggle the service off if you do not want to include it in your order.
8. On the **Summary** pane, review the instance settings and the estimated price.
7. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Related links
{: #tenant-ordering-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
