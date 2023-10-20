---

copyright:

  years:  2023

lastupdated: "2023-10-13"

keywords: veeam, veeam install, tech specs veeam

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Managing Veeam for {{site.data.keyword.vmware-service_short}}
{: #tenant-veeam}

The Veeam® Backup and Replication service is available and ready to use in your {{site.data.keyword.vmware-service_full}} instance. This service seamlessly integrates as a managed solution to help your enterprise achieve high availability and provides recovery points for your applications and data. By using this service, you control the backup of all virtual machines (VMs) for your infrastructure directly from the Veeam console.

Service charges are incurred only if you choose to include the service in your order.

For multitenant instances, you must install the Veeam service after you provision your virtual data center (VDC). For more information, see [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting).

For single-tenant instances, the service is included by default in your {{site.data.keyword.vmware-service_short}} Cloud Director site order. You can remove the service from your initial order and add the service to an existing single-tenant Cloud Director site.

The Veeam service is configured with seven days of immutability by default. All backups are deleted after seven days. If more time is needed, open an IBM Support ticket to increase the number of days.
{: note}

## Accessing the Veeam self-service portal
{: #tenant-veeam-portal}

The Veeam Backup and Replication service has visibility to back up VMs from any virtual data center (VDC) in the organization. It is available at the VMware® Cloud Director organization level for any VMware Cloud Director user with the **Organization Administrator** role.

When you use the Veeam self-service portal to create backup jobs, you can choose any VM instance from any virtual data center in the organization.

You can access the Veeam portal from the **Add-on services** tab of the VDC instance details page when the status of the virtual data center is **Available**.

### Procedure to access the Veeam self-service portal from the instance
{: #tenant-veeam-portal-proc-access}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. Click the instance type tab.
   * For multitenant instances, click the **Cloud director sites** tab. Then, click the instance name.
   * For single-tenant instances, click the **Virtual data centers** tab. Then, click the instance name.
3. Click the **Add-on services** tab on the instance details page, then click **Veeam backups**.
4. Use a user with the Organization Administrator role to log in to the Veeam self-service portal. A newly provisioned virtual data center's **admin** user has the role by default.

Alternatively, click the **More** menu in the VMware Cloud Director tenant portal and select **Data Protection with Veeam**.

If you do not see the **Data Protection with Veeam** option, open an IBM Support ticket by following the steps in [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support). In the subject for your issue, include **Request Veeam Self Service Portal for my Organization** and include your Organization ID and virtual data center name in your issue description.
{: note}

## Licenses and fees for Veeam Backup and Replication
{: #tenant-pricing-services}

Veeam usage incurs the following charges. You can view the charges on the {{site.data.keyword.cloud_notm}} **Manage > Billing and usage** view.

In the {{site.data.keyword.cloud_notm}} **Usage** view, locate the **{{site.data.keyword.vmware-service_short}}** service. Locate the **Organization** plan to find the Veeam usage across all virtual data centers in that organization.

Review the following table to understand Veeam for {{site.data.keyword.vmware-service_short}} single-tenant pricing.

For more information about Licenses and fees for Veeam Backup and Replication for {{site.data.keyword.vmware-service_short}} multitenant, see [VMware as a Service multitenant pricing](/docs/vmware-service?topic=vmware-service-mt_pricing).
{: note}

| Metric                                   | Frequency   | Description |
|:-----------------------------------------|:------------|:------------|
| VEEAM_BACKUP_SERVICE_BASE_CHARGE | Monthly | Provisioning charge per instance where Veeam is enabled. |
| VEEAM_BACKUP_HOST_CHARGE | Monthly | Utilization charge on the number of bare metal servers with VMs that use Veeam backups. |
| ORG_VEEAM_LICENSES | Monthly | Veeam license charge for every VM under backup. The monthly charge is for the highest number of VMs under backup at any time period in the month. |
| ORG_VEEAM_BLOCK_STORAGE | Hourly | Charge per GB of block storage used for all backups. |
| ORG_VEEAM_OBJECT_STORAGE | Hourly | Charge per GB of object storage used for all backups. |
{: caption="Table 1. Licenses and fees for Veeam" caption-side="bottom"}

For the Veeam service, all backups go to both the block storage cross-data center and to Cloud Object Storage.



## Backup data storage and encryption
{: #tenant-veeam-storage}

Veeam Backup and Replication backup storage uses a unique scale-out backup repository (SOBR) object for each customer. The SOBR is programmatically configured for each customer, with a dedicated location on each disk and a generated backup file encryption password. The SOBR includes an extent that is backed by IBM block storage in each of the physical data centers within the specific region. For example, if the virtual data center is in **Dallas 10**, the SOBR has extents in either **Dallas 12** or **Dallas 13** depending on which one has more storage when the Veeam service was added. The SOBR includes a customer-specific Cloud Object Storage bucket for more cost-effective long-term storage and as a second copy. Depending on the regions and compliance requirements of each geography, the Cloud Object Storage buckets remain in the same country, which is sometimes the same physical site.

When you decide to use the Veeam self-service portal to create backup jobs, identify which VM instances from any virtual data center in the organization participate in the backup job. Those backups are stored in the organizations SOBR.

You can manage (restore or delete) backups in the Veeam self-service portal. All backups are deleted if a virtual organization is deleted.

## Limitations for Veeam Backup and Replication
{: #tenant-veeam-portal-limitations}

* For the Veeam **application aware image processing** and **guest file system indexing** options to work for Windows® VMs, the most recent VMware® Tools must be installed on the VMs. Linux® VMs do not support application awareness or guest file system indexing.
* If you are using **application aware image processing** for MS SQL or Oracle DB backups, the options **application aware** and **Item** restore are not supported. The restore operation needs to complete a full VM restore, which requires a downtime window for any consumers of the database.
* An immutable backup failure cannot be manually retried. You must run active full backup or wait for the next scheduled backup to run. For more information, see [Managing Cloud Director Backups](https://helpcenter.veeam.com/docs/backup/vsphere/vcloud_manage_backup.html?ver=120){: external}.

## Related links
{: #tenant-veeam-related}

* [Viewing {{site.data.keyword.vmware-service_short}} multitenant instances](/docs/vmware-service?topic=vmware-service-tenant-viewing-mt)
* [Viewing {{site.data.keyword.vmware-service_short}} single-tenant instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center](https://www.veeam.com/documentation-guides-datasheets.html){: external}
