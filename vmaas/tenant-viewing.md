---

copyright:

  years: 2022

lastupdated: "2022-12-15"

keywords: view tenant instance, single tenant instances, view instance, single tenant view

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing}

View the summary and detailed information of the {{site.data.keyword.vmware-service_short}} instances that are provisioned in your account.

## Procedure to view a summary of {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, view the list of instances that are provisioned.
3. Review the name, region, creation time, and status of the provisioned instances.

## Procedure to view details for {{site.data.keyword.vmware-service_short}} instances
{: #tenant-viewing-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
2. On the **Summary** tab, view the number of clusters, virtual data centers (VDCs), provider VDCs, and other instance site details.
3. In the **Access controls** section, you can:
   * Enable IAM (Identity Access Management) for existing sites by clicking **Set IAM integration**. For more information, see [Managing resource groups](/docs/account?topic=account-rgs).
   * Reset the site administrator password by clicking **Reset site admin password**.
4. Click the **Infrastructure** tab.
   * On the **Clusters** tab, view all clusters that are deployed into the instance. Click a cluster name to review information such as total cores and RAM, host units, and cluster status.
   * Click the **Data centers** tab to view all VDCs deployed into the instance. Click a VDC to review information such as public IP addresses.
   * Click the **Network edges** tab to view the edges deployed into the instance.

## Related links
{: #tenant-viewing-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
