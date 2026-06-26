---

copyright:

  years: 2026

lastupdated: "2026-06-25"

keywords: veeam backups, sobr, vcf as a service migration, migration, COS bucket, IBM Cloud Object Storage

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Migrating Veeam Backup options from shared SOBRs to {{site.data.keyword.cloud_notm}} Object Storage-only SOBRs
{: #veeam-migrating-cos}

{{site.data.content.vms-deprecated-note}}

To simplify your migration from {{site.data.keyword.vmware-service_notm}}, you can migrate your Veeam backups (for versions 12 or later) and redirect your existing backup jobs from the existing *shared* SOBRs to the *dedicated* SOBRs, which is the {{site.data.keyword.cloud_notm}} Object Storage-only Scale out Backup Repository (SOBR).

Open an {{site.data.keyword.cloud_notm}} support ticket to request to import and migrate your {{site.data.keyword.cloud_notm}} Object Storage buckets during your environment migration. When your migration is complete, you can restore backups from your Cloud Object Storage-only SOBR.

## Procedure to request to migrate IBM Cloud Object Storage buckets
{: #veeam-migrating-cos-proc}

1. Go to the [{{site.data.keyword.cloud_notm}} Support Center](/unifiedsupport/supportcenter){: external}.
2. Scroll down the page, and click **Create case**.
3. Under the **Category** section, click **All topics**.
4. In the **Topic** section, select `VMware Cloud Foundation as a Service` for **Topic**, and select `Other` for **Subtopic**. Click **Next**.
5. Under the **Details** section, provide the following details, and then click **Next**.

   * For **Subject**, type **Migrate Veeam Backup options from shared SOBRs to {{site.data.keyword.cloud_notm}} Object Storage-only SOBRs**.
   * For **Description**, provide the following details so that {{site.data.keyword.IBM_notm}} Support can personalize your request to help ensure a smooth setup process:
      * For `Cloud Object Storage` details, specify the IBM Cloud Object Storage instance name and region name.
      * For `Cloud Object Storage bucket` details, specify the IBM Cloud Object Storage bucket name and folder name.
      * For `Cloud Object Storage credentials`, specify the IBM Cloud Object Storage access key ID and secret access.

6. **Review** the details, and click **Submit case**.

After you submit the case, a confirmation email is sent to you with a case number for your records. The {{site.data.keyword.IBM_notm}} Support team reviews your request, and if required, contacts you for further information.

## Post-migration steps
{: #veeam-post-migrating-cos}

After you migrate the Cloud Object Storage buckets, complete the following steps:

* Restore your data from existing or earlier backups.
* Back up the new OS images from {{site.data.keyword.vmware-service_short}}.
* Retain a local copy of your own Cloud Object Storage bucket backups to help ensure continuity after the service term ends.

## Related links
{: #veeam-migrating-cos-links}

* [Managing Veeam for VCF as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Migrating workloads to VCF as a Service with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
