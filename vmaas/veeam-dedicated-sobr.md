---

copyright:

  years: 2024, 2025

lastupdated: "2025-09-11"

keywords: add veeam sobr, veeam adding sobr, scale-out backup repository

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Using cost-effective Veeam Backup options with a dedicated Scale-out Backup Repository 
{: #veeam-adding-sobr}

A Scale-out Backup Repository (SOBR) is a data repository target for backup jobs that are configured in the Veeam® Backup service. This storage solution is designed to support horizontal scaling through its multitier system, which consists of a performance tier and an optional capacity tier. The performance tier can either be a set of vSAN™ repositories or two Cloud Object Storage repositories. Additionally, if a capacity tier is specified, it is either a pair of Cloud Object Storage repositories if the performance tier has vSAN repositories, or it is two Cloud Object Storage repositories if the performance tier has Cloud Object Storage repositories.

{{site.data.keyword.vmware-service_full}} offers cost-effective Veeam Backup options that include *shared* SOBRs and *dedicated* SOBRs that improve scale, performance, and provide additional consumption options.

When you provision your {{site.data.keyword.vcf-aas-full}} instance, a total of two *shared* SOBRs are created by default through the Veeam Backup service. The default shared SOBRs include performance tier storage that is backed by vSAN and capacity tier storage that is backed by {{site.data.keyword.cloud_notm}} Object Storage, each with a maximum size of 100 TB and 7 days of immutability. You cannot change the configuration or delete default SOBRs.

All default backups are deleted after seven days. If more time is needed, open an IBM Support ticket to increase the number of days.
{: note}

If you do not require the performance tier vSAN storage option or need more storage than the shared SOBRs offer, you can order a *dedicated* SOBR for your single-tenant and multitenant instances. Add a dedicated SOBR of a minimum size of 200 TB or multiple 200 TB repository virtual machines (VMs) to create a SOBR up to a maximum of 1200 TBs. The repository VMs for a dedicated SOBR are not shared.

The following SOBR types are available when you request a dedicated SOBR. You are billed monthly for the vSAN and {{site.data.keyword.cloud_notm}} Object Storage SOBR option and no charge for the {{site.data.keyword.cloud_notm}} Object Storage only SOBR options.

* vSAN and {{site.data.keyword.cloud_notm}} Object Storage, two copies.
* {{site.data.keyword.cloud_notm}} Object Storage only, one local and one remote copy.
* {{site.data.keyword.cloud_notm}} Object Storage only, one local copy

*vSAN and {{site.data.keyword.cloud_notm}} Object Storage* is the recommended SOBR type for rapid disaster recovery scenarios. *{{site.data.keyword.cloud_notm}} Object Storage only* SOBR types are recommended exclusively for larger data volumes and slower disaster recovery scenarios.

For {{site.data.keyword.cloud_notm}} Object Storage immutability, the Veeam Backup service retains the backup up to an additional 30 days.



## Procedure to request a dedicated SOBR
{: #veeam-adding-sobr-proc}

You must request a size less than or equal to a specified maximum size (1200 TB) and divisible evenly by 200 TB.
{: requirement}

1. Go to the [{{site.data.keyword.cloud_notm}} Support Center](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}.
2. Scroll down and click **Create a case**.
3. In the **Category** section of the **Create a case** page, complete the following selections.
    1. For **Topic**, select `IBM Cloud Backup - Veeam`.
    2. For **Subtopic**, select `Veeam Scale Out Backup Repository`.
    3. Select the **All topics** tile and click **Next**.
4. In the **Details** section, provide the following information and then click **Next**.
    1. For **Subject**, enter `Request to Add New Dedicated SOBR to Veeam Instance`
    2. For **Description**, provide the following details to help IBM Support tailor the repository to meet your specific data protection needs and to help ensure a smooth setup process.

    * `Site ID:` Specify the unique director site identifier where the SOBR is configured. For multitenant instances, use the site ID of the multitenant instance owner's account.
    * `SOBR name:` Specify the name of your dedicated SOBR. This name is used to identify the repository in your Veeam management console.
    * `Type:` Specify the storage type of the performance tier of the SOBR as either **vSAN** or **Cloud Object Storage**. For the Cloud Object Storage type, specify either **One local Cloud Object Storage** or **Two copy (one local and one remote) Cloud Object Storage**.
    * `SOBR size:` Specify the required storage capacity for the performance tier as **Performance Tier Size**, in increments of 200 TB. If the vSAN or Two Copy Cloud Object Storage type is specified for the performance tier, specify a size for the capacity tier as **Capacity Tier Size**, in increments of 200 TB.
    * `Data center:` Specify the data center with available storage clusters where you want to deploy the SOBR. Consider your current and anticipated storage needs. You must provide a value that includes the data center region and number. For example, `dal12`.

5. In the **Review** section, review the case details and click **Submit case**.

After you submit the case, you receive a confirmation email with a case number for your records. The IBM Support team reviews your request and might contact you for further information. The typical setup time can take up to three days.

## Procedure to update a dedicated SOBR
{: #veeam-update-sobr-proc}

You can open an IBM Support case to request to update an existing dedicated SOBR on your Veeam instance. You must include the following details to complete the request:

* `Site ID:` Specify the unique director site identifier where the SOBR is configured. For multitenant instances, use the site ID of the multitenant instance owner's account.
* `Account ID:` Specify the account ID that is associated with your customer account.
* `SOBR name:` Specify the name of your dedicated SOBR. This name is used to identify the repository in your Veeam management console.
* `SOBR size:` Indicate the new required storage capacity for the SOBR. The new size must be greater than the existing size and divisible evenly by 200 TB.

## Procedure to delete a dedicated SOBR
{: #veeam-delete-sobr-proc}

You can open an IBM Support case to request to delete an existing dedicated SOBR on your Veeam instance. You must include the following details to complete the request:

* `Site ID:` Specify the unique director site identifier where the SOBR is configured. For multitenant instances, use the site ID of the multitenant instance owner's account.
* `Account ID:` Specify the account ID that is associated with your customer account.
* `SOBR name:` Specify the name of your dedicated SOBR. This name is used to identify the repository in your Veeam management console.

## Related links
{: #veeam-adding-sobr-links}

* [Getting help and support for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-support)
* [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center Technical Documentation](https://helpcenter.veeam.com/){: external}
