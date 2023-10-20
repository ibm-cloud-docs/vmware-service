---

copyright:

  years: 2023

lastupdated: "2023-10-03"

keywords: bring your own key, key management

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Configuring the key provider
{: #key-management}

 {{site.data.keyword.vmware-service_full}} provides IBM-managed keys to protect your virtual machines (VMs) that use encrypted storage policies. For *single-tenant* instances, you can bring your own managed key provider.

## Before you begin
{: #key-management-prereq}

You must complete the following before you contact customer support to configure your managed key provider.

* Ensure that the single-tenant instance is in **Available** status.
* Create and prepare either a Key Protect (KP) instance or a Hyper Protect Crypto Services (HPCS) instance. Then, configure a KMIP™ for VMware instance that is connected to the KP or HPCS instance. For more information, see [Connecting the key management server](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-implementation#kmip-implementation-connecting-kms).

## Limitations for key management support
{: #key-management-limitations}

* Key management is supported only for single-tenant instances and not for multitenant instances.
* You must apply encrypted storage profiles to your VMs to encrypt the machines using your key provider. If you have any existing encrypted VMs, they are re-keyed to your key provider as part of this process.
* VMs can experience cryptographic erasure and become inoperable if you remove any of the following instances or keys. The VMs may not become inoperable immediately.
    * KMIP for VMware instance
    * Key Protect instance
    * Hyper Protect instance
    * Any of the keys with the above instances
* The following procedure applies only to VM encryption. Your backup data is still protected by using IBM-managed keys.

## Procedure to request configuration for a customer managed key provider
{: #key-management-procedure}

Open an {{site.data.keyword.cloud_notm}} Support ticket request to configure a customer managed key provider. For more information, see [Getting help and support for VMware as a Service](/docs/vmware-service?topic=vmware-service-support).

You must provide the following information in your support ticket request.
* Enter `Customer managed key provider for single-tenant VMware as a Service instance` in the issue subject.
* Provide the connection information for your KMIP for VMware instance.

   1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** > **KMIP for VMware** from the left navigation pane.
   2. In the **KMIP for VMware** table, click the instance.
   3. From the **KMIP for VMware** instance details page, make note of the hostname that is listed under **KMIP server endpoints**.

     * For Key Protect, make note of the two hostnames.
     * For HPCS, make note of the single URL making sure to include the port number.

After you open the support ticket request, IBM provides certificate details that you must enter into your KMIP for VMware instance. The certificate details allow the VMware management plane to access your key provider.


## Related links
{: #key-management-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
