---

copyright:

  years: 2023

lastupdated: "2023-11-15"

keywords: vmware as a service, price for vmware as a service, pricing plan, single-tenant pricing

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vmware-service_short}} single-tenant pricing
{: #st_pricing}

{{site.data.keyword.vmware-service_full}} single-tenant offers pay-as-you-go with monthly charges for the dedicated VMware infrastructure components. The components include bare metal servers, storage, networking, and add-on services. You can grow and shrink the VMware deployment based on your needs.

## Licenses and fees for Veeam Backup and Replication
{: #st-pricing-services}

Veeam usage incurs the following charges. You can view the charges on the {{site.data.keyword.cloud_notm}} **Manage > Billing and usage** view.

In the {{site.data.keyword.cloud_notm}} **Usage** view, locate the **{{site.data.keyword.vmware-service_short}}** service. Locate the **Organization** plan to find the Veeam usage across all virtual data centers in that organization.

Review the following table to understand Veeam for {{site.data.keyword.vmware-service_short}} single-tenant pricing.

For more information about licenses and fees for Veeam Backup and Replication for {{site.data.keyword.vmware-service_short}} multitenant, see [VMware as a Service multitenant pricing](/docs/vmware-service?topic=vmware-service-mt_pricing).
{: note}

| Metric                                   | Frequency   | Description |
|:-----------------------------------------|:------------|:------------|
| VEEAM_BACKUP_SERVICE_BASE_CHARGE | Monthly | Provisioning charge per instance where Veeam is enabled. |
| VEEAM_BACKUP_HOST_CHARGE | Monthly | Utilization charge on the number of bare metal servers with VMs that use Veeam backups. |
| ORG_VEEAM_LICENSES | Monthly | Veeam license charge for every VM under backup. The monthly charge is for the highest number of VMs under backup at any time period in the month. |
| ORG_VEEAM_BLOCK_STORAGE | Hourly | Charge per GB of block storage used for all backups. |
| ORG_VEEAM_OBJECT_STORAGE | Hourly | Charge per GB of object storage used for all backups. |
{: caption="Table 1. Licenses and fees for Veeam single-tenant instances" caption-side="bottom"}

For the Veeam service, all backups go to both the block storage cross-data center and to Cloud Object Storage.

## Related links
{: #st_pricing-related}

* [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [VMware as a Service multitenant pricing](/docs/vmware-service?topic=vmware-service-mt_pricing)
* [VMware Cloud Director](https://docs.vmware.com/en/VMware-Cloud-Director/10.4/VMware-Cloud-Director-Tenant-Portal-Guide/GUID-74C9E10D-9197-43B0-B469-126FFBCB5121.html){: external}
