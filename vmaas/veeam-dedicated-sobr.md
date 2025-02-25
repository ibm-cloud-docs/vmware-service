---

copyright:

  years: 2024, 2025

lastupdated: "2025-02-24"

keywords: add veeam sobr, veeam adding sobr, scale-out backup repository

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Using a dedicated Scale-out Backup Repository with Veeam Backup
{: #veeam-adding-sobr}

When you provision your {{site.data.keyword.vmware-service_full}} instance, a total of two *shared* Scale-out Backup Repository (SOBRs) are available. The size of each shared SOBR is a maximum of 100 TB.

A SOBR is a repository system with horizontal scaling support for multitier storage of data and consists of one or more backup repositories or object storage repositories that are called the performance tier. You can expand the performance tier with object storage repositories for long-term retention to create the capacity tier. All of the storage devices and systems inside the SOBR are joined into a system with their capacities summarized.

If you require more storage than the shared SOBRs offer, you can order a *dedicated* SOBR through the Veeam® Backup service for your single-tenant and multitenant instances. You can add a SOBR of a minimum size of 200 TB or multiple 200 TB repository virtual machines (VMs) to create a SOBR up to a maximum of 1200 TBs. The repository VMs for a SOBR are not shared.

For more information about SOBRs with Veeam Backup, see the *Backup data storage and encryption* section in [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam#tenant-veeam-storage).

To order a dedicated SOBR, you must open a new IBM Support case and provide the following information. You can order multiple SOBRs.

## Procedure to request a dedicated SOBR
{: #veeam-adding-sobr-proc}

You must request a size less than or equal to a specified maximum size (1200 TB) and divisible evenly by 200 TB.
{: requirement}

1. Go to the [{{site.data.keyword.cloud_notm}} Support Center](https://cloud.ibm.com/unifiedsupport/supportcenter).
2. Scroll down and click **Create a case**.
3. In the **Category** section of the **Create a case** page, complete the following selections.
    1. For **Topic**, select `IBM Cloud Backup - Veeam`.
    2. For **Subtopic**, select `Veeam Scale Out Backup Repository`.
    3. Select the **All topics** tile and click **Next**.
4. In the **Details** section, provide the following information and then click **Next**.
    1. For **Subject**, enter `Request to Add New Dedicated SOBR to Veeam Instance`
    2. For **Description**, provide the following details to help IBM Support tailor the repository to meet your specific data protection needs and to ensure a smooth setup process.

    * `Site ID:` Specify the unique director site identifier where the SOBR is configured. For multitenant instances, use the site ID of the multitenant instance owner's account.
    * `SOBR name:` Specify the name of your dedicated SOBR. This name is used to identify the repository in your Veeam management console.
    * `SOBR size and data center:` Indicate the required storage capacity for the SOBR and the data center with available storage clusters where you want to deploy the SOBR. Consider your current and anticipated storage needs. You must provide a value that includes the data center region and number. For example, `dal12`.

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
* [Veeam Help Center Technical Documentation](https://www.veeam.com/support/help-center-technical-documentation.html?productId=8&version=product%3A8%2F221){: external}
