---

copyright:

  years: 2022, 2023

lastupdated: "2023-01-23"

keywords: order tenant instance, single tenant instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering}

You can order an {{site.data.keyword.vmware-service_full}} instance from the VMware Solutions user interface after you review the minimum requirements.

## Minimum requirements for {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering-min-req}

The minimum instance order must contain:
   * 2 hosts (2 Sockets - 32 Cores and 192 GB RAM)
   * 1 unit of 24 TB of 2 IOPS/GB NFS storage

You can start with just one virtual data center (VDC) and a performance network edge of medium size.

## Procedure to order {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering-procedure}

1. In the VMware Solutions console, click **Create** on the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** page, enter the instance name and select a resource group.

   If **No resource group available** is displayed, you currently do not have the permission to add VDCs to any resource group in this account. Contact the account owner to be assigned the **Editor** or **Administrator** role on a resource group in the account. For more information, see [IAM roles](/docs/account?topic=account-userroles).
3. Specify the settings for the provider virtual data center (PVDC).
    1. Specify the PVDC name.
    2. Select the geography, region, and data center to host the PVDC.
4. Specify the settings for the cluster.
    1. Specify the cluster name.
    2. Select the host profile.
    3. Specify the host quantity (minimum 2).
    4. Specify the sizings for one or more IOPS/GB performance tiers for attached NFS storage.
5. On the **Summary** pane, review the instance settings and the estimated price.
6. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Related links
{: #tenant-ordering-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
