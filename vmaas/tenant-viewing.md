---

copyright:

  years: 2022, 2023

lastupdated: "2022-09-06"

keywords: view tenant instance, single tenant instances, view instance, single tenant view

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} instances that are provisioned in your account.

## Procedure to view a summary of {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click either the **Virtual data centers** tab or the **Cloud director sites** tab to view the list of instances that are provisioned.
3. Review the name, location, and status of the provisioned instances.

## Procedure to view details for {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click either the **Virtual data centers** tab or the **Cloud director sites** tab. Then, click an instance name.
2. On the **Summary** tab, review the virtual data center or Cloud Director site details.
3. For virtual data centers, the following options are available.
   * On the **Summary** tab, toggle fast provisioning off or on.
   * On the **Add-on services** tab, you can:
     * Enable or delete Veeam® Backup and Replication.
     * Click **Veeam backups** to open the Self-Service Backup Portal.
4. For Cloud Director sites, the following options are available.
   * On the **Summary** tab, you can click **Enable Veeam Backup and Replication** to provision the recommended service for your instance.
   * On the **Infrastructure** tab, you can:
     * Click the **Clusters** tab, view all clusters that are deployed into the instance. Click a cluster name to review information such as total cores and RAM, host units, storage type, and cluster status.
     * Click the **Virtual data centers** tab to view all VDCs deployed into the instance. Click a VDC to review information such as public IP addresses.
     * Click the **Network edges** tab to view the edges deployed into the instance.
   * On the **Add-on services** tab, you can:
     * Enable or delete Veeam Backup and Replication.
     * Click **Veeam backups** to open the Self-Service Backup Portal.

## Related links
{: #tenant-viewing-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
