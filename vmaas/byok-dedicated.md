---

copyright:

  years: 2025

lastupdated: "2025-09-16"

keywords: dedicated workloads, virtual machine encryption, bring your own key, vm encryption, IBM Key Protect

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Bring Your Own Key for dedicated workloads
{: #byok-dedicated}

An {{site.data.keyword.keymanagementservicefull}} instance is provided when you provision your {{site.data.keyword.vmware-service_notm}} instance or you can Bring Your Own Key (BYOK) for dedicated workload virtual machine (VM) encryption. An {{site.data.keyword.keymanagementservicelong_notm}} instance is required for customer-managed keys. Review the following important requirements to ensure that your VMs work properly with the encryption.

## Understanding your responsibilities when you use Key Protect
{: #byok-dedicated-key-protect}

Review the following documentation for details on roles and responsibilities for managing your {{site.data.keyword.keymanagementserviceshort}} instance.

* [FAQ for {{site.data.keyword.keymanagementserviceshort}}](/docs/key-protect?topic=key-protect-faqs&interface=ui)
* [Understanding high availability and disaster recovery for {{site.data.keyword.keymanagementserviceshort}}](/docs/key-protect?topic=key-protect-ha-dr)
* [Your responsibilities when using {{site.data.keyword.keymanagementserviceshort}}](/docs/key-protect?topic=key-protect-shared-responsibilities#disaster-recovery)

## Understanding your responsibilities when you BYOK
{: #byok-dedicated-customer}

Review the following to understand critical responsibilities when you manage your own {{site.data.keyword.keymanagementserviceshort}} instance. It is your responsibility to work with {{site.data.keyword.keymanagementservicelong_notm}} support for recovery, if necessary.
{: important}

* **Removing a {{site.data.keyword.keymanagementserviceshort}} instance**: If you delete or disable your {{site.data.keyword.keymanagementserviceshort}} instance, the KMS encryption keys and KMS instance sever the decryption path for any workloads that are hosted on {{site.data.keyword.vcf-aas-full}} in {{site.data.keyword.cloud_notm}}.
* **Renewing a {{site.data.keyword.keymanagementserviceshort}} certificate**: You must create an {{site.data.keyword.IBM_notm}} Support case to notify {{site.data.keyword.vcf-aas}} engineers before any certificate rotation associated with {{site.data.keyword.keymanagementserviceshort}} to ensure proper coordination and to prevent unintended service disruptions.

## Before you begin
{: #byok-dedicated-before}

If you have existing workloads to migrate to the new {{site.data.keyword.keymanagementserviceshort}} instance, you must schedule a maintenance window with {{site.data.keyword.IBM_notm}} Support to rekey the existing workloads. You must schedule the maintenance window outside of your backup window.

* The time to rekey depends on the number of existing workloads.
* Each workload to rekey must not have a snapshot.
* The expected behavior during the rekey is that the VMs remain operational.

## Procedure to request to Bring Your Own Key
{: #byok-dedicated-proc}

1. Go to the [{{site.data.keyword.cloud_notm}} Support Center](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}.
2. Scroll down and click **Create case**.
3. In the **Category** section, click **All topics**.
4. In the **Topic** section, select the following:
    1. For **Topic**, select `VMware Cloud Foundation as a Service`.
    2. For **Subtopic**, select `Other` and click **Next**.
4. In the **Details** section, provide the following information and then click **Next**.
    1. For **Subject**, enter `Bring Your Own Key for a {{site.data.keyword.vcf-aas}} instance`
    2. For **Description**, provide the following details to help {{site.data.keyword.IBM_notm}} Support tailor your needs and to help ensure a smooth setup process.

    * `Detailed description:` Request that {{site.data.keyword.vcf-aas}} engineers configure the {{site.data.keyword.vcf-aas}} instance to point to your customer provisioned {{site.data.keyword.keymanagementservicelong_notm}} instance.
    * `Private endpoint URL:` Specify the private endpoint URL and port of your {{site.data.keyword.keymanagementservicelong_notm}} instance.
    
    To find your private endpoint URL, navigate to **IBM Cloud > Resources > Security > *Key_Protect_instance* > Endpoints**. 
    
    Identify the instance private endpoint in the following format: `private.[region].kms.cloud.ibm.com:[port]`. For example, `private.us-south.kms.cloud.ibm.com:5696`.

5. In the **Review** section, review the case details and click **Submit case**.

After you submit the case, you receive a confirmation email with a case number for your records. The {{site.data.keyword.IBM_notm}} Support team configures your endpoint and provides the {{site.data.keyword.vcf-aas}} certificate.

## Next steps
{: #byok-dedicated-next}

After the {{site.data.keyword.IBM_notm}} Support team provides you with the {{site.data.keyword.vcf-aas}} certificate, you must import it to your {{site.data.keyword.keymanagementserviceshort}} instance. For more information about certificates, see *Step 4* in [Creating an adapter](/docs/key-protect?topic=key-protect-kmip&interface=ui#kmip-adapter-create).

Refer to the support case number to confirm that the operation is complete and request that {{site.data.keyword.vcf-aas}} engineers validate that the trust relationship is healthy. The {{site.data.keyword.vcf-aas}} engineers complete any necessary rekey workloads and provide confirmation when the work is complete.

## Related links
{: #byok-dedicated-links}

* [Shared responsibilities for using {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities)
* [Understanding your responsibilities when you use {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-understand-responsib)
* [Understanding data portability for VMware Cloud Foundation as a Service](/docs/vmware-service?topic=vmware-service-data-portability)
* [Getting help and support for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-support)
