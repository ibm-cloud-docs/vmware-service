---

copyright:

  years:  2022, 2023

lastupdated: "2023-01-26"

keywords: set IAM integration, iam roles, manage iam, SSO, single sign on

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Director single sign-on with IBM Cloud IAM
{: #iam-integration}

Authentication and authorization to VMware Cloud Director defaults to using {{site.data.keyword.cloud}} IAM (Identity and Access Management). Users log in to VMware Cloud Director by using their {{site.data.keyword.cloud_notm}} credentials. When logged in to the {{site.data.keyword.cloud_notm}} account with the {{site.data.keyword.vmware-service_short}} instance, single sign-on (SSO) is used to access VMware Cloud Director.

## Before you begin
{: #iam-integration-prereq}

Review roles and assign resource access for {{site.data.keyword.vmware-service_short}} instances. For more information, see [Managing IAM access for {{site.data.keyword.vmware-service_short}}](/docs/vmware-service?topic=vmware-service-iam&interface=ui) and [Roles and permissions for VMware Cloud Director](/docs/vmware-service?topic=vmware-service-iam_vcd).

## Responsibilities when you use IAM
{: #iam-integration-responsib}

Review the following information to understand your responsibilities and {{site.data.keyword.IBM}} responsibilities for managing IAM.

### IBM responsibilities
{: #iam-integration-responsib-ibm}

Review IBM responsibilities for managing IAM.

* Configure the IAM integration with the VMware Cloud Director console by using OpenID Connect (OIDC) for new deployments.
* In the VMware Cloud Director console, populate the initial roles and permissions that map to the IAM roles. For more information, see [Roles and permissions for VMware Cloud Director](/docs/vmwaresolutions?topic=vmwaresolutions-iam_vcd&interface=ui).

### Your responsibilities
{: #iam-integration-responsib-user}

Review your responsibilities for managing IAM.

* Maintain and manage the {{site.data.keyword.cloud_notm}} IAM SSO integration with VMware Cloud Director.
* User roles and permissions are managed in {{site.data.keyword.cloud_notm}} IAM.
* Remove or disconnect the {{site.data.keyword.cloud_notm}} IAM integration with VMware Cloud Director if you want local authentication (auth-n) and authorization (auth-z) through VMware Cloud Director
* Users are added to VMware Cloud Director and managed directly in VMware Cloud Director with roles and permissions.

## Procedure to re-enable IBM Cloud IAM SSO integration for VMware Cloud Director
{: #iam-integration-procedure}

You can disable SSO configuration disabled in VMware Cloud Director. When SSO is disabled, local authentication (auth-n) and authorization (auth-z) is managed locally in VMware Cloud Director by adding users in Director and creating policies in Director for the users. Use the following steps to reset the VMware Cloud Director configurations back to using {{site.data.keyword.cloud_notm}} IAM for auth-n and auth-z.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
3. On the **Summary** tab for the instance, under **Access Controls**, click **Set IAM integration**.

## Results after you enable IAM
{: #iam-integration-results}

The IAM integration status can have the following results.

| Status | Description |
|:------ |:----------- |
| Integration pending | The IAM integration is in progress. |
| Integration incomplete | The integration is not successful. Contact IBM Support. |
| Integration enabled | The IAM integration was previously enabled for the organization. You can reset the integration, if needed. |
{: caption="Table 1. Status descriptions for IAM implementation" caption-side="bottom"}

### Removing or disconnecting the IBM Cloud IAM integration with VMware Cloud Director
{: #iam-integration-results-reset}

Before you can reset the IAM integration, you must delete all OpenID Connect (OIDC) users and imported groups with the OIDC type, then delete the OIDC provider. For more information, see [Deleting the OpenID Connect configuration in your VMware Cloud Director organization](/docs/vmwaresolutions?topic=vmwaresolutions-shared_vcd-ops-guide#shared_vcd-ops-guide-delete-oidc).

### Single sign-on availability
{: #iam-integration-results-sso}

After the IAM integration is enabled, you can use single sign-on to log in to the VMware Cloud Director console.

1. Click **VMware Cloud Director console**.
2. From the log in panel, click **SIGN IN WITH SINGLE SIGN-ON** to log in to the console.

## Related links
{: #iam-integration-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview&interface=ui)
* [Viewing and deleting VDCs](/docs/vmware-service?topic=vmware-service-vdc-view-delete&interface=ui)
* [Contacting IBM Support](/docs/vmware-service?topic=vmware-service-support&interface=ui)
* [VMware Cloud Director](https://www.vmware.com/products/cloud-director.html){: external}
