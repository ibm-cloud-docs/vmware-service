---

copyright:

  years: 2023

lastupdated: "2023-10-18"

keywords: add veeam, delete veeam, veeam adding, veean remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting Veeam Backup and Replication
{: #veeam-adding-deleting}

You can add the Veeam® Backup and Replication service to your Cloud Director site instance if you did not include it in your instance order. You can delete the Veeam service from your instance if you no longer need the backup service.

For multitenant instances, you must install the Veeam service after you provision your virtual data center (VDC).
{: requirement}

Before you delete the Veeam Backup and Replication service from your instance, review the following considerations.

* Block storage backups are permanently deleted.
* {{site.data.keyword.cloud}} Object Storage offload storage backups are maintained for seven days after the service removal, and then is permanently deleted.
* You have seven days after the Veeam service is deleted to open a support ticket to restore backups. For more information, see [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support).
* The Veeam base, hosts, and license charges continue until the end of month.
* Storage charges stop as the storage areas are permanently deleted.

## Procedure to add Veeam Backup and Replication to {{site.data.keyword.vmware-service_short}} instances
{: #veeam-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click **Available services**.
5. On the **Add-on services** window, toggle Veeam Backup and Replication on.
6. Review the new cost, select the confirmation checkboxes, and click **Add**.

## Procedure to delete Veeam Backup and Replication to {{site.data.keyword.vmware-service_short}} instances
{: #veeam-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click the vertical overflow menu in the Veeam Backup and Replication panel and click **Delete**.
5. In the **Delete add-on service** window, review the considerations, and enter **Veeam Backup and Replication** to confirm that you want to delete all Veeam backup services from your instance. Click **Delete**.

## Related links
{: #veeam-adding-deleting-links}

* [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Managing Veeam for VMware as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center](https://www.veeam.com/documentation-guides-datasheets.html){: external}
