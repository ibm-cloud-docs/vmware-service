---

copyright:
  years: 2022, 2025

lastupdated: "2025-10-30"

keywords: data encryption in vmware service, data storage for vmware service, bring your own keys for vmware service, BYOK for vmware service, key management for vmware service, key encryption for vmware service, personal data in vmware service, data deletion for vmware service, data in vmware service, data security in vmware service, KYOK for vmware service

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Securing your data in {{site.data.keyword.vcf-aas}}
{: #vmaas-data-security}

{{site.data.content.vms-deprecated-note}}

To ensure that you can securely manage your data when you use {{site.data.keyword.vmware-service_notm}}, it is important to know exactly what data is stored and encrypted and how you can delete any stored data. All {{site.data.keyword.vcf-aas-full}} instances come with encryption enabled that uses a unique cloud provider key per instance. Each {{site.data.keyword.vcf-aas}} instance is configured with the following unique resources:

* Dedicated {{site.data.keyword.keymanagementserviceshort}} instance
* Dedicated keys per instance
* Dedicated KMIP™ adapter per instance
{: shortdesc}

## How your data is stored and encrypted in {{site.data.keyword.vcf-aas}}
{: #vmaas-data-security-storage}

The {{site.data.keyword.vcf-aas}} data plane consists of the following types of data:
* Customer {{site.data.keyword.vcf-aas}} instance metadata
* Customer data

All data types and all solution data are regionally isolated. For each region that is supported by the {{site.data.keyword.vcf-aas}} offering, all runtime data is maintained within region. The exception is backup data, which is isolated inside the regions geo-political boundaries for data resiliency if a full region disaster occurs.

## Protecting your sensitive data in {{site.data.keyword.vcf-aas}}
{: #vmaas-data-security-encryption}

### Customer {{site.data.keyword.vcf-aas}} instance metadata
{: #vmaas-data-security-cust-metadata}

This data is client metadata that is associated with the created {{site.data.keyword.vcf-aas}} instance.

{{site.data.keyword.vcf-aas}} is public in that the same service is supporting many different customers. As instances are created, modified, and deleted by customers, metadata about each customer instance is maintained by the service. The instance metadata describes the details of the {{site.data.keyword.vcf-aas}} instances.

Some of the metadata is collected directly from the customer and other metadata is generated as an artifact of the automation logic that is used to order and configure the instance such as the hosts, storage, networking, and service data. Instance metadata includes:

* Client cloud account and contact information
* Instance names and IDs of VMware® by Broadcom instances that are deployed for customers
* VMware® by Broadcom instances locations
* Installed services, for example, Veeam®, Zerto, or HCX™
* Deployment state of each instance, for example Deploying, Failed, or Ready
* Configuration of user solutions and the underlying components that are used in customer solutions (Compute, networking, storage, licenses)
* Credentials to access the underlay IaaS and VMware by Broadcom components that are hosting the customers' workloads
* Management logs generated from automation
* Support data that is associated with helping the client resolve issues and questions

{{site.data.keyword.vcf-aas}} does not collect any client or special personal information.
{: note}

### About customer-managed keys
{: #vmaas-data-security-about-encryption}

Customer keys (BYOK) are not initially supported. {{site.data.keyword.vcf-aas}} generates the keys uniquely per instance.

## Deleting your data in {{site.data.keyword.vcf-aas}}
{: #vmaas-data-security-data-delete}

### Deleting {{site.data.keyword.vcf-aas}} metadata
{: #vmaas-data-security-data-delete-metadata}

Client metadata is associated with the VMware by Broadcom instances that the client creates. When the VMware by Broadcom instance is deleted by the client that the metadata is maintained in the DB where the instance state is set to deleted. Client metadata is maintained in the DB unless the client specifically requests that the data is removed by using a support ticket.

Logs and support data that is associated with the instance are retained by {{site.data.keyword.cloud_notm}} policy for 1 year unless requested for deletion through an {{site.data.keyword.cloud_notm}} ticket.

### Deleting {{site.data.keyword.vcf-aas}} customer data
{: #vmaas-data-security-data-delete-cust-data}

{{site.data.keyword.vcf-aas}} customer data is deleted including any customer backups of data by using the service in association with the deletion of the service instance. The cloud service provided data encryption key used by customers to encrypt data is destroyed on deletion. This event renders the data unusable there forward.

## Related links
{: #vmaas-data-security-links}

* [Data protection](/docs/vmware-service?topic=vmware-service-architecture-workload-isolation-learning#architecture-workload-isolation-data-protection)
* [Data and data protection for client-owned data](/docs/vmware-service?topic=vmware-service-architecture-workload-isolation-learning#architecture-workload-isolation-data-client)
