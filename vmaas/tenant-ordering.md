---

copyright:

  years: 2022, 2023

lastupdated: "2023-10-19"

keywords: order tenant instance, single tenant instances, order instance, single tenant order

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Cloud Director site instances
{: #tenant-ordering}

You can create an {{site.data.keyword.vmware-service_full}} single-tenant Cloud Director site from the VMware Solutions user interface. First review the minimum requirements.

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
* The provider virtual data center (PVDC) is set to **pvdc-_xx_**.
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
4. Select the Cloud Director geography and location.
5. Specify the settings for the provider virtual data center (PVDC).
    1. Specify the PVDC name.
    2. Select the PVDC location.
    3. Optionally toggle SAP-certified server profiles on and select the profile type.
6. Specify the settings for the cluster.
    1. Specify the cluster name.
    2. Select the profile storage type.
    3. Select the host profile.
    4. Select the host quantity.
       * For NFS only storage, select a minimum of 2.
       * For vSAN storage, select a minimum of 7.
    5. For vSAN, optionally select the **Enable vSAN de-duplication & compression** checkbox to save storage space.
    6. Select the sizings for one or more IOPS/GB performance tiers for attached NFS storage.
7. Review the add-on service option to deploy the Veeam® Backup and Replication service. Toggle the service off if you do not want to include it in your order.
8. On the **Summary** pane, review the instance settings and the estimated price.
7. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Related links
{: #tenant-ordering-links}

* [Viewing {{site.data.keyword.vmware-service_short}} multitenant instances](/docs/vmware-service?topic=vmware-service-tenant-viewing-mt)
* [Viewing {{site.data.keyword.vmware-service_short}} single-tenant instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud_notm}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
