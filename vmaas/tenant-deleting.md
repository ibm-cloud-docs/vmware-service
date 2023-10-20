---

copyright:

  years: 2022, 2023

lastupdated: "2023-10-18"

keywords: delete tenant instance, single tenant instances, delete instance, single tenant delete

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Deleting {{site.data.keyword.vmware-service_short}} instances
{: #tenant-deleting}

When you no longer need them, you can delete the {{site.data.keyword.vmware-service_full}} instances that are provisioned in your account.

You cannot delete a single-tenant Cloud Director site instance if it still has virtual data centers (VDCs) in it. Before you delete your Cloud Director site, ensure that all VDC instances in the site are deleted.

For multitenant instances, you can only delete VDCs. The Cloud Director site is automatically deleted when the last VDC in the region is deleted.

## Procedure to delete {{site.data.keyword.vmware-service_short}} instances
{: #tenant-deleting-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click either the **Virtual data centers** tab or the **Cloud director sites** tab. Then, click the instance that you want to delete.
3. Click the **Actions...** menu, and then click **Delete instance**.
4. Confirm that you want to delete the instance.

   The status of the {{site.data.keyword.vmware-service_short}} instance is changed to **Deleting**. When the instance is deleted successfully, the instance components are released, and the status is changed to **Deleted**.

Alternatively, you can click the delete icon located in the instance row of the {{site.data.keyword.vmware-service_short}} **Virtual data centers** or **Cloud Director sites** summary table.
{: fast-path}

## Related links
{: #tenant-deleting-links}

* [Ordering {{site.data.keyword.vmware-service_short}} virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Ordering {{site.data.keyword.vmware-service_short}} Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering-mt)
* [Visualizing your site with {{site.data.keyword.cloud_notm}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
