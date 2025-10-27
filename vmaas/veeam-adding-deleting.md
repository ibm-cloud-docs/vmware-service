---

copyright:

  years: 2023, 2025

lastupdated: "2025-10-24"

keywords: add veeam, delete veeam, veeam adding, veean remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting Veeam Backup
{: #veeam-adding-deleting}

{{site.data.content.vms-deprecated-note}}

You can add the Veeam® Backup service to your Cloud Director site instance if you did not include it in your instance order. You can delete the Veeam service from your instance if you no longer need the backup service.

For multitenant instances, you must install the Veeam service after you provision your virtual data center (VDC).
{: requirement}

Before you delete the Veeam Backup service from your instance, review the following considerations.

* Block storage backups are permanently deleted.
* {{site.data.keyword.cloud}} Object Storage offload storage backups are maintained for seven days after the service removal, and then is permanently deleted.
* You have seven days after the Veeam service is deleted to open a support ticket to restore backups. For more information, see [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support).
* The Veeam base, hosts, and license charges continue until the end of month.
* Storage charges stop as the storage areas are permanently deleted.

## Procedure to add Veeam Backup to {{site.data.keyword.vcf-aas}} instances
{: #veeam-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Add-on services** tab.
4. Click **Add service**.
5. In the **Add-on services** pane, toggle Veeam Backup on.
6. Review the new cost, select the confirmation checkboxes, and click **Add**.

## Procedure to delete Veeam Backup from {{site.data.keyword.vcf-aas}} instances
{: #veeam-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Add-on services** tab.
4. Click the vertical overflow menu in the **Veeam Backup** panel and click **Delete service**.
5. In the **Delete add-on service** pane, review the considerations, and enter **Veeam Backup** to confirm that you want to delete all Veeam backup services from your instance. Click **Delete**.

## Related links
{: #veeam-adding-deleting-links}

* [Ordering {{site.data.keyword.vcf-aas}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center Technical Documentation](https://helpcenter.veeam.com/){: external}
