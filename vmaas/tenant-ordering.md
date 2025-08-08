---

copyright:

  years: 2022, 2025

lastupdated: "2025-08-07"

keywords: order tenant instance, cloud director site instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Cloud Director site instances
{: #tenant-ordering}

You can create an {{site.data.keyword.vmware-service_full}} single-tenant Cloud Director site from the VMware Solutions user interface. First, review the minimum requirements.

{{site.data.keyword.vcf-aas-full}} multitenant Cloud Director site instances are ordered and managed by {{site.data.keyword.IBM}}. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).

On the **{{site.data.keyword.vmware-service_short}}** order page, click [See pricing details](/vmware/vmware_as_a_service/provision/vdc_st) to view the rate card that outlines cost details by feature. For more information, see [VCF as a Service pricing](/docs/vmware-service?topic=vmware-service-vmaas_pricing).
{: note}

## Name requirements
{: #tenant-ordering-vdc-name}

The Cloud Director site infrastructure names are set by default, where _xx_ represents two randomly generated alphabetic characters.
* The Cloud Director site name is set to **inst-_xx_**.
* The resource pool is set to **rp-_xx_**.
* The cluster name is set to **cluster-_xx_**.

You can specify a name that meets the following requirements:
* The maximum length is 50 characters.
* The name must start with an alphabetic character.
* Only alphanumeric, dash (-), underscore (_), and space characters are allowed.
* The name must be unique within all active names in your account. You can reuse a name that is previously deleted.

## Procedure to order {{site.data.keyword.vcf-aas}} Cloud Director site instances
{: #tenant-ordering-procedure}

Some host profiles might not be available for a selected location. Contact your IBM Sales representative to request missing host profiles.
{: note}

1. In the VMware Solutions console, click the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** order page, click the **Single-tenant Cloud Director site** card.
3. Specify the Cloud Director site name and select a resource group.

   If **No resource group available** is displayed, you currently do not have the permission to add VDCs to any resource group in this account. Contact the account owner to assign the **Editor** or **Administrator** role on a resource group in the account. For more information, see [{{site.data.keyword.IBM_notm}} IAM roles](/docs/account?topic=account-userroles).
4. Select the geography and region for the site location.
5. Specify the settings for the resource pool.
    1. Specify the resource pool name.
    2. Select the resource pool location.
    3. Optionally enable SAP®-certified server profiles and select the profile type.
6. Specify the settings for the cluster.
    1. Specify the cluster name.
    2. Select the profile CPU type.
    2. Select the profile storage type.
    3. Select the host profile.
    4. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN storage, select a minimum of 7.
    5. For vSAN, optionally select the **Enable vSAN de-duplication & compression** checkbox to save storage space.
    6. Select the sizings for one or more IOPS/GB performance tiers for attached NFS storage.
7. Specify the network connectivity settings.
    * Complete the following steps for management connectivity.
       1. Select either public-only or private-only networking.
       2. For private-only, click **Add new +** and enter the subnet value. Then, click the **Save** icon. Repeat for all of the subnets that you want to add.
    * For workload connectivity, select either public and private networking or private-only networking.
8. Review the add-on service options to deploy the Veeam® Backup service and the VMware Cloud Director Availability service. Toggle the service off if you do not want to include it in your order.
8. In the **Summary** panel, review the instance settings and the estimated price.
7. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Provisioning a virtual data center - resource group considerations
{: #tenant-ordering-rg-reqs}

Review the following considerations before you order a {{site.data.keyword.vcf-aas}} VDC.

Even though you can place your {{site.data.keyword.vcf-aas}} VDCs into different resource groups, the resource group differentiation is useful only for billing purposes. For access control, IAM policies are tested against the Cloud Director site and not the VDCs.

For single-tenant VDCs, select the resource group for the Cloud Director site.

Because {{site.data.keyword.cloud_notm}} checks against the Cloud Director site resource group rather than the VDC resource group, users with permission to create a VDC can create one in any resource group.

When you use resource groups for IAM access, keep the Cloud Director site and all of the VDCs in the Cloud Director site in the same resource group.
{: tip}

## Related links
{: #tenant-ordering-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
* [Managing resource groups](/docs/account?topic=account-rgs&interface=ui)
* [Visualizing your site with {{site.data.keyword.cloud_notm}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
