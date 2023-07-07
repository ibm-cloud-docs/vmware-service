---

copyright:

  years: 2022, 2023

lastupdated: "2023-07-06"

keywords: delete tenant instance, single tenant instances, delete instance, single tenant delete

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Deleting {{site.data.keyword.vmware-service_short}} instances
{: #tenant-deleting}

When you no longer need them, you can delete the {{site.data.keyword.vmware-service_full}} instances that are provisioned in your account.

You cannot delete an instance if it still has virtual data centers (VDCs) in it. Before you delete your instance, ensure that all VDCs in the instance are deleted.
{: restriction}

## Procedure to delete {{site.data.keyword.vmware-service_short}} instances
{: #tenant-deleting-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab. Then, click the instance that you want to delete.
3. Click the **Actions...** menu, and then click **Delete instance**.

   The status of the {{site.data.keyword.vmware-service_short}} instance is changed to **Deleting**. When the instance is deleted successfully, the instance components are released, and the status is changed to **Deleted**.

## Related links
{: #tenant-deleting-links}

* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
