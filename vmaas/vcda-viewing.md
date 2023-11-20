---

copyright:

  years: 2023

lastupdated: "2023-11-16"

keywords: view vcda details

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing VMware Cloud Director Availability details
{: #vcda-viewing}

View the summary and detailed information for migrating your virtual machines (VMs) to {{site.data.keyword.vmware-service_full}} with VMware Cloud Director Availability (VCDA).

## Procedure to view a summary of VMware Cloud Director Availability details
{: #vcda-viewing-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click a single-tenant instance name.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. Review the estimated VMware Cloud Director Availability summary details.

   * In the **Migration estimated capacity** section, review the range of VMs to migrate, the number of VMware Cloud Director Availability instances, and the resources that are required for the provider virtual data center (PVDC) to migrate VMs. Resources include the number of replicators, RAM, and CPU per instance.

   Click **Edit capacity** to edit the estimated migration capacity. For more information, see [Adding migration capacity](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding).

   * In the **Instance endpoints and connections** section, review the instance endpoint type and connection details. You can also add new endpoints for private connections for an additional charge.

### VMware Cloud Director Availability instance endpoint details
{: #vcda-viewing-instance-ep}

On the **Instance endpoints** tab, review the zone, the connection type of public or private, the site name, and the replication endpoint.

The **Site name** and **Replication endpoint** columns provide the option to **Copy to clipboard** for the site and endpoint names. Use the site name of your instance to connect your on-premises peers. Use the replication endpoint URL to connect to the peer from your on-premises instance.

Click **Add private endpoint** to add new endpoints for private connections. For more information, see [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep).

## Related links
{: #vcda-viewing-links}

* [VMware Cloud Director Availability for {{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
