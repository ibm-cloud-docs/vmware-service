---

copyright:

  years:  2023, 2024

lastupdated: "2024-07-03"

keywords: veeam, veeam install, tech specs veeam

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Managing Veeam for {{site.data.keyword.vcf-aas}}
{: #tenant-veeam}

The Veeam® Backup and Replication service is available and ready to use in your {{site.data.keyword.vmware-service_full}} instance. This service seamlessly integrates as a managed solution to help your enterprise achieve high availability and provides recovery points for your applications and data. By using this service, you control the backup of all virtual machines (VMs) for your infrastructure directly from the Veeam console.

Service charges are incurred only if you choose to include the service in your order.

For multitenant instances, you must install the Veeam service after you provision your virtual data center (VDC). For more information, see [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting).

For single-tenant instances, the service is included by default in your {{site.data.keyword.vcf-aas-full}} Cloud Director site order. You can remove the service from your initial order and add the service to an existing single-tenant Cloud Director site.

The Veeam service is configured with seven days of immutability by default. All backups are deleted after seven days. If more time is needed, open an IBM Support ticket to increase the number of days.
{: note}

## Accessing the Veeam self-service portal
{: #tenant-veeam-portal}

The Veeam Backup and Replication service has visibility to back up VMs from any VDC in the organization. It is available at the VMware® Cloud Director organization level for any VMware Cloud Director user with the **Organization Administrator** role.

When you use the Veeam self-service portal to create backup jobs, you can choose any VM instance from any virtual data center in the organization.

You can access the Veeam portal from the **Add-on services** tab of the VDC instance details page when the status of the virtual data center is **Available**.

### Procedure to access the Veeam self-service portal from the instance
{: #tenant-veeam-portal-proc-access}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. Click the instance type tab.
   * For multitenant instances, click the **Cloud director sites** tab. Then, click the instance name.
   * For single-tenant instances, click the **Virtual data centers** tab. Then, click the instance name.
3. Click the **Add-on services** tab on the instance details page, then click **Veeam backups**.
4. Use a user with the Organization Administrator role to log in to the Veeam self-service portal.

Alternatively, click the **More** menu in the VMware Cloud Director tenant portal and select **Data Protection with Veeam**.

If you do not see the **Data Protection with Veeam** option, open an IBM Support ticket by following the steps in [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support). In the subject for your issue, include **Request Veeam Self Service Portal for my Organization** and include your Organization ID and virtual data center name in your issue description.
{: note}

## Backup data storage and encryption
{: #tenant-veeam-storage}

Veeam Backup and Replication backup storage uses a unique scale-out backup repository (SOBR) object for each customer. The SOBR is programmatically configured for each customer, with a dedicated location on each disk and a generated backup file encryption password. The SOBR includes an extent that is backed by IBM block storage in each of the physical data centers within the specific region. For example, if the virtual data center is in **Dallas 10**, the SOBR has extents in either **Dallas 12** or **Dallas 13** depending on which one has more storage when the Veeam service was added. The SOBR includes a customer-specific Cloud Object Storage bucket for more cost-effective long-term storage and as a second copy. Depending on the regions and compliance requirements of each geography, the Cloud Object Storage buckets remain in the same country, which is sometimes the same physical site.

When you decide to use the Veeam self-service portal to create backup jobs, identify which VM instances from any virtual data center in the organization participate in the backup job. Those backups are stored in the organizations SOBR.

You can manage (restore or delete) backups in the Veeam self-service portal. All backups are deleted if a virtual organization is deleted.

## IBM policy for data protection with Veeam
{: #tenant-veeam-policy}

You can configure the Veeam service in various ways. Some options include self-service, but in all cases IBM defaults to keeping backup restore points and chains. Consider the following IBM policies for data protection with Veeam.

### Backup job creation
{: #tenant-veeam-policy-backup-job-create}

When you create a backup job, you add VMs or vApps to the job for data protection and also define the backup job schedule. The IBM policy is to never remove your VMs or vApps from your backup jobs or to delete any backups without your permission.

### Removal of backups
{: #tenant-veeam-policy-backup-remove}

To remove backups, you can choose to remove VMs or vApps from the backup job or delete VMs or vApps that were previously backed up. In either case, you are responsible for deleting the old restore points. Before you remove VMs or vApps or delete the restore points, consider the following information.

#### Backup chain format
{: #tenant-veeam-policy-backup-remove-chain}

Starting with Veeam 12, the IBM policy uses per-machine backup with separate metadata files for backup chain format. For more information, see [Backup Chain Formats](https://helpcenter.veeam.com/docs/backup/vsphere/per_vm_backup_files.html?ver=120){: external}.

#### Backup job retention policy
{: #tenant-veeam-policy-backup-remove-retention}

The backup retention policy defines how many restore points to retain on disk. After the allowed number of restore points is exceeded, Veeam applies the retention policy to remove the earliest restore point from the backup chain. Depending on your business requirements, it is your responsibility to set the retention policy when you create the backup job. For more information, see [Short-Term Retention Policy](https://helpcenter.veeam.com/docs/backup/vsphere/retention_policy.html?ver=120){: external}.

You can update the retention policy at a later time. However, the new settings are applied only to the new data and cannot be applied to previous data that maintains the previous retention policy setting.
{: note}

#### Backup immutability at Performance Tier
{: #tenant-veeam-policy-backup-remove-perf-tier}

Immutability prohibits deletion of data by making that data temporarily immutable. The IBM policy is to set the backup immutability at the performance tier to seven days. For more information, see [Immutability for Performance Tier](https://helpcenter.veeam.com/docs/backup/vsphere/immutability_performance_tier.html?ver=120){: external}.

#### Removal of restore points
{: #tenant-veeam-policy-backup-remove-restore-points}

Veeam keeps at least one full backup chain and doesn't remove old restore points until a second full backup (synthetic or active) is created and a new backup chain starts. For more information, see [Removal of Restore Points](https://helpcenter.veeam.com/docs/backup/vsphere/retention_separate_vms.html?ver=120){: external}.

#### Retention policy for deleted items
{: #tenant-veeam-policy-backup-remove-ret-delete}

Veeam has the **Remove deleted items data after** setting available for each backup job to delete restore points for deleted items after a set number of days. The IBM policy does not enable this setting by default, but can enable the setting when a support case is opened. You must provide the following information in the support case to enable the setting.

* The name of the backup jobs where you want to enable the setting.
* The value, in days, to set for the **Remove deleted items data after** setting.

When this option is enabled, the restore points for any VM or vApp that is no longer processed by the backup job is permanently deleted after the set number of days.
{: important}

For more information, see [Retention Policy for Deleted Item](https://helpcenter.veeam.com/docs/backup/vsphere/retention_deleted_vms.html?ver=120){: external}.

The retention policy is applied only if the job stops creating backups for the entire vApp. Therefore, a removal of VMs within vApps does not result in automatic deletion of those restore points. It is your responsibility to delete the restore points.
{: note}

### Moving items between backup jobs
{: #tenant-veeam-policy-backup-moving-between}

You can move VMs or vApps between backup jobs. Any VM or vApp that you move to a new backup job results in a new backup chain and restore points under the new backup job. Removing the original backup and restore points in this case falls into the same category as removing backups. You are responsible for deleting the original restore points.

## Limitations for Veeam Backup and Replication
{: #tenant-veeam-portal-limitations}

* For the Veeam **application aware image processing** and **guest file system indexing** options to work for Windows® VMs, the most recent VMware Tools™ must be installed on the VMs. Linux® VMs do not support application awareness or guest file system indexing.
* If you are using **application aware image processing** for MS SQL or Oracle DB backups, the options **application aware** and **Item** restore are not supported. The restore operation needs to complete a full VM restore, which requires a downtime window for any consumers of the database.
* An immutable backup failure cannot be manually retried. You must run active full backup or wait for the next scheduled backup to run. For more information, see [Managing Cloud Director Backups](https://helpcenter.veeam.com/docs/backup/vsphere/vcloud_manage_backup.html?ver=120){: external}.

## Related links
{: #tenant-veeam-related}

* [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center Technical Documentation](https://www.veeam.com/support/help-center-technical-documentation.html?productId=8&version=product%3A8%2F221){: external}
