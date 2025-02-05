---

copyright:

  years: 2023, 2025

lastupdated: "2025-01-21"

keywords: view vcda details

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing VCDA details
{: #vcda-viewing}

View the summary and detailed information for migrating and protecting your virtual machines (VMs) to {{site.data.keyword.vmware-service_full}} with VMware Cloud Director Availability (VCDA).

## Procedure to view a summary of VMware Cloud Director Availability details
{: #vcda-viewing-summary}

Use the **Migration estimated capacity** section for both migration and protection destination configurations.
{: note}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click a single-tenant instance name.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. Review the VCDA configuration and summary details.

   * For single-tenant instances, you can configure the capacity based on the estimated number of VMs you plan to migrate or protect. In the **Migration estimated capacity** section, review the range of VMs to migrate or protect, the number of VCDA instances, and the resources that are required for the resource pool to migrate or protect VMs. Resources include the number of replicators, RAM, and CPU per instance.

     For multitenant instances, the capacity is monitored and scaled by {{site.data.keyword.IBM_notm}}.
     {: note}

      For a single-tenant Cloud Director site instance, click **Edit capacity** to edit the estimated capacity. For more information, see [Adding capacity to single-tenant Cloud Director sites with VCDA](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding).

   * In the **Instance endpoints and connections** section, review the instance endpoint type and connection details. You can also add new endpoints for private connections for an additional charge.

### Instance endpoint details
{: #vcda-viewing-instance-ep}

The following details are available for instance endpoints.

On the **Instance endpoints** tab, review the zone, the connection type of public or private, the site name, and the replication endpoint. The following options are also available.

* The **Site name** and **Replication endpoint** columns provide the option to **Copy to clipboard** for the site and endpoint names. Use the site name of your instance to connect your on-premises peers. Use the replication endpoint URL to connect to the peer from your on-premises instance.
* Click **Open VCDA** to access the VCDA console.
* Click **Add private endpoint** to add new endpoints for private connections. For more information, see [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep).

### VMware Shared pairing details
{: #vcda-viewing-shared}

The following details are available for VMware Shared pairings.

On the **VMware Shared pairings** tab, you can review the source and peer zones, the source and peer site names, and the status.

The **Source site name** and **Peer site name** columns provide the option to **Copy to clipboard**.

### {{site.data.keyword.vcf-aas}} pairing details
{: #vcda-viewing-vmwaas}

The following details are available for {{site.data.keyword.vcf-aas-full}} pairings.

On the **{{site.data.keyword.vcf-aas}} pairings** tab, you can review the source and peer zones, the source and peer site names, and the status.

The **Source site name** and **Peer site name** columns provide the option to **Copy to clipboard**.

Click the overflow menu at the end of the endpoint or pairing row to view details.
{: tip}

## Related links
{: #vcda-viewing-links}

* [Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
