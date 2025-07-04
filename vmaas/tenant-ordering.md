---

copyright:

  years: 2022, 2025

lastupdated: "2025-07-02"

keywords: order tenant instance, cloud director site instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Cloud Director site instances
{: #tenant-ordering}

You can create an {{site.data.keyword.vmware-service_full}} single-tenant Cloud Director site from the VMware Solutions user interface. First, review the minimum requirements.

{{site.data.keyword.vcf-aas-full}} multitenant Cloud Director site instances are ordered and managed by {{site.data.keyword.IBM}}. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).
{: note}

## Billing details
{: #tenant-ordering-billing}

On the {{site.data.keyword.vmware-service_short}} order page, click the [**About** tab](/vmware/vmware_as_a_service/provision/vdc_st) to view complete pricing details.

| Feature                      | Billing model      |
|:-----------------------------|:-------------------|
| Single-tenant host profiles | - Hosts are billed monthly. \n - Hosts that you order after the first day of the month are prorated for the first month. \n - Hosts that are removed during the month are charged for the full month that they are removed. \n - Each host is treated individually. For example, when you remove a host then add a host, the bill reflects two hosts for that month. |
| Single-tenant shared storage | - Shared storage is billed monthly. \n - Storage that is ordered after the first day of the month is prorated for the first month. \n - Storage that is removed during the month is charged for the full month that it is removed. \n - Each storage change is treated individually. For example, when you remove storage then add storage, the bill reflects both storages for that month. |
| Single-tenant edge storage | - Edge storage is billed monthly. \n - Edges that are ordered after the first day of the month are prorated for the first month. \n - Edges that are removed during the month are charged for the full month that they are removed. \n - Each edge change is treated individually. For example, when you remove an edge then add an edge, the bill reflects both edges for that month. \n - For an efficiency edge, one edge instance is used with 1-64 VRF (virtual edges). One efficiency edge can support up to 64 virtual data centers (VDCs) until the next edge instance is deployed. When an efficiency edge reaches attachment of zero VDCs the efficiency edge is removed. |
{: caption="Billing details" caption-side="bottom"}

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
