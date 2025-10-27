---

copyright:

  years:  2022, 2025

lastupdated: "2025-10-24"

keywords: iam user role for vmware, iam user, iam roles, manage iam, SSO, single sign on

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Director single sign-on with IBM Cloud IAM
{: #iam-integration}

{{site.data.content.vms-deprecated-note}}

You can use the VMware Cloud Director™ console to configure and manage the {{site.data.keyword.vmware-service_full}} virtual data centers (VDCs). VMware® by Broadcom workloads are created, deployed, and managed in the VMware Cloud Director console.

Access the VMware Cloud Director console from the VMware Solutions console to complete the following tasks from the console.

* Virtual machine (VM) templates upload
* vApp and VM deployment and management
* Virtual network creation and management
* Edge configuration and putting VMs on the public and private networks
* User administration

Authentication and authorization to VMware Cloud Director defaults to using {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM). Users log in to VMware Cloud Director by using their {{site.data.keyword.cloud_notm}} credentials. When logged in to the {{site.data.keyword.cloud_notm}} account with the {{site.data.keyword.vcf-aas-full}} instance, single sign-on (SSO) is used to access VMware Cloud Director.

In the VMware Solutions console, click **VMware console** to access the VMware Cloud Director console.

## Before you begin
{: #iam-integration-prereq}

Review roles and assign resource access for {{site.data.keyword.vcf-aas}} instances. For more information, see [Managing IAM access for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui) and [Roles and permissions for VMware Cloud Director](/docs/vmware-service?topic=vmware-service-vmaas-iam_vcd).

## Responsibilities when you use IAM
{: #iam-integration-responsib}

Review the following information to understand your responsibilities and {{site.data.keyword.IBM}} responsibilities for managing IAM.

### IBM responsibilities
{: #iam-integration-responsib-ibm}

Review IBM responsibilities for managing IAM.

* Configure the IAM integration with the VMware Cloud Director console by using OpenID Connect (OIDC) for new deployments.
* In the VMware Cloud Director console, populate the initial roles and permissions that map to the IAM roles. For more information, see [Roles and permissions for VMware Cloud Director](/docs/vmware-service?topic=vmware-service-vmaas-iam_vcd).

### Your responsibilities
{: #iam-integration-responsib-user}

Review your responsibilities for managing IAM.

* Maintain and manage the {{site.data.keyword.cloud_notm}} IAM SSO integration with VMware Cloud Director.
* User roles and permissions are managed in {{site.data.keyword.cloud_notm}} IAM.
* Remove or disconnect the {{site.data.keyword.cloud_notm}} IAM integration with VMware Cloud Director if you want local authentication (auth-n) and authorization (auth-z) through VMware Cloud Director.
* Users are added to VMware Cloud Director and managed directly in VMware Cloud Director with roles and permissions.

## Related links
{: #iam-integration-links}

* [{{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview&interface=ui)
* [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support&interface=ui)
* [VMware Cloud Director Documentation](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director.html){: external}
