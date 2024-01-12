---

copyright:

  years: 2022, 2024

lastupdated: "2024-01-02"

keywords: order tenant instance, cloud director site instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Cloud Director site instances
{: #tenant-ordering}

You can create an {{site.data.keyword.vmware-service_full}} single-tenant Cloud Director site from the VMware Solutions user interface. First, review the minimum requirements.

{{site.data.keyword.vmware-service_short}} multitenant Cloud Director site instances are ordered and managed by {{site.data.keyword.IBM}}. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).
{: note}

## Minimum requirements for {{site.data.keyword.vmware-service_short}} instances
{: #tenant-ordering-min-req}

Minimum 2 servers (7 servers for vSAN™ profiles)
 * 2 hosts (2-socket 32 cores, 192 GB RAM)
 * 24 TB of shared storage
 * Minimum of 1 virtual data center (VDC) with a medium performance edge

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

## Procedure to order {{site.data.keyword.vmware-service_short}} Cloud Director site instances
{: #tenant-ordering-procedure}

1. In the VMware Solutions console, click **Create** on the **{{site.data.keyword.vmware-service_short}}** card.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the **VMwaaS single-tenant Cloud Director site** card.
3. Specify the Cloud Director site name and select a resource group.

   If **No resource group available** is displayed, you currently do not have the permission to add VDCs to any resource group in this account. Contact the account owner to assign the **Editor** or **Administrator** role on a resource group in the account. For more information, see [{{site.data.keyword.IBM_notm}} IAM roles](/docs/account?topic=account-userroles).
4. Select the Cloud Director geography and region.
5. Specify the settings for the resource pool.
    1. Specify the resource pool name.
    2. Select the resource pool location.
    3. Optionally enable SAP®-certified server profiles and select the profile type.
6. Specify the settings for the cluster.
    1. Specify the cluster name.
    2. Select the profile storage type.
    3. Select the host profile.
    4. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN storage, select a minimum of 7.
    5. For vSAN, optionally select the **Enable vSAN de-duplication & compression** checkbox to save storage space.
    6. Select the sizings for one or more IOPS/GB performance tiers for attached NFS storage.
7. Review the add-on service options to deploy the Veeam® Backup and Replication service and the VMware Cloud Director Availability service. Toggle the service off if you do not want to include it in your order.
8. On the **Summary** pane, review the instance settings and the estimated price.
7. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Related links
{: #tenant-ordering-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Viewing and deleting {{site.data.keyword.vmware-service_short}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
* [Viewing and deleting {{site.data.keyword.vmware-service_short}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
* [Visualizing your site with {{site.data.keyword.cloud_notm}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
