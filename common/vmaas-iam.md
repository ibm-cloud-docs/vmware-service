---

copyright:
  years:  2022, 2025

lastupdated: "2025-10-24"

keywords: IAM access for vmware service, permissions for vmware service, identity and access management for vmware service, roles for vmware service, actions for vmware service, assigning access for vmware service

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Managing IAM access for {{site.data.keyword.vcf-aas}}
{: #vmaas-iam}

{{site.data.content.vms-deprecated-note}}

Access to {{site.data.keyword.vmware-service_full}} instances for users in your account is controlled by {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM). Every user that accesses {{site.data.keyword.vcf-aas-full}} in your account must be assigned an access policy with an IAM role. Review the following roles, actions, and more to help determine the best way to assign access to {{site.data.keyword.vcf-aas}}.
{: shortdesc}

The access policy that you assign users in your account determines the actions that a user can complete within the context of the service or specific instance that you select. The allowable actions are customized and defined by {{site.data.keyword.vcf-aas}} as operations that are allowed to on the service. Each action is mapped to an IAM platform or service role that you can assign to a user.

If a specific role and its actions don't fit the use case that you're looking to address, you can [create a custom role](/docs/account?topic=account-custom-roles&interface=ui) and pick the actions to include.
{: tip}

IAM access policies enable access to be granted at different levels. Some of the options include the following accesses:

* Access across all instances of the service in your account
* Access to an individual service instance in your account
* Access to a specific resource within an instance

Review the following tables that outline what types of tasks each role allows for when you're working with {{site.data.keyword.vcf-aas}}. Platform management roles enable users to complete tasks on service resources at the platform level. For example, assign user access to the service, create, delete or scale instances, and bind instances to applications. Service access roles enable users to access {{site.data.keyword.vcf-aas}}. For more information about the exact actions that are mapped to each role, see [IAM roles and actions](/docs/account?topic=account-iam-service-roles-actions).

| Platform role | Description of actions |
|:------------- |:---------------------- |
| Viewer | View VMware® by Broadcom instances, clusters, hosts, storage, services, virtual data centers, and dashboards. |
| Operator | View or update VMware by Broadcom instances, add and remove hosts, storage, and clusters, and install VMware by Broadcom services. |
| Editor | In addition to all Operator permissions, create and delete VMware by Broadcom instances. |
| Administrator | In addition to all Operator permissions, reset the admin credentials for VMware by Broadcom instances. |
{: row-headers}
{: class="simple-tab-table"}
{: caption="IAM platform roles" caption-side="bottom"}
{: #iamrolesplatform}
{: tab-title="Platform roles"}
{: tab-group="IAM"}

| Service role | Description of actions |
|:------------ |:---------------------- |
| Reader | View VMware by Broadcom and Usage Meter instances, virtual data centers, and dashboards. |
| Writer | View VMware by Broadcom and Usage Meter instances, also add and remove services to virtual data centers. |
| Manager | In addition to all Writer permissions, create and delete virtual data centers, and reset the admin credentials for VMware by Broadcom instances. |
| VCFaaS Director Full Viewer | All view access to every component in VMware Cloud Director™. |
| VCFaaS Director vApp Author | Use catalogs and create vApps in VMware Cloud Director. |
| VCFaaS Director vApp User | Use existing vApps in VMware Cloud Director. |
| VCFaaS Director Catalog Author | Create and publish catalogs in VMware Cloud Director. |
| VCFaaS Director Network Admin | Create, view, edit, delete the subnet, the static route, and troubleshoot routing in VMware Cloud Director. |
| VCFaaS Director Console User | View a virtual machine state, properties, and use the guest operating system in VMware Cloud Director. |
| VCFaaS Director Backup User | Manage Veeam® backup jobs in VMware Cloud Director. |
| VCFaaS Director Security Admin | View and edit the edge firewall and the distributed firewall in VMware Cloud Director. |
{: row-headers}
{: class="simple-tab-table"}
{: caption="IAM service access roles" caption-side="bottom"}
{: #iamrolesservice}
{: tab-title="Service roles"}
{: tab-group="IAM"}

## Resource group considerations
{: #vmaas-iam-rg-reqs}

For access control, IAM policies are tested against the Cloud Director site and not the VDCs.

Even though you can place your {{site.data.keyword.vcf-aas}} VDCs into different resource groups, the resource group differentiation is useful only for billing purposes.

For single-tenant VDCs, select the resource group for the Cloud Director site.

For multitenant VDCs, your Cloud Director site is placed in the same resource group as the first VDC in any region.

Because {{site.data.keyword.cloud_notm}} checks against the Cloud Director site resource group rather than the VDC resource group, users with permission to create a VDC can create one in any resource group.

When you use resource groups for IAM access, keep the Cloud Director site and all of the VDCs in the Cloud Director site in the same resource group.
{: tip}

## Assigning access to {{site.data.keyword.vcf-aas}} in the console
{: #assign-access-console}
{: ui}

You can assign access in the console in one of the following ways:

* Access policies per user. You can manage access policies per user from the **Manage** > **Access (IAM)** > **Users** page in the console. For more information about the steps to assign IAM access, see [Managing access to resources](/docs/account?topic=account-assign-access-resources&interface=ui).
* Access groups. Access groups are used to streamline access management by assigning access to a group once. Then, you can add or remove users as needed from the group to control their access. You manage access groups and their access from the **Manage** > **Access (IAM)** > **Access groups** page in the console. For more information, see [Assigning access to a group in the console](/docs/account?topic=account-groups&interface=ui#access_ag).
