---

copyright:

  years: 2023, 2024

lastupdated: "2024-10-03"

keywords: add private endpoint, VMware Cloud Director Availability

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting private instance endpoints with VCDA
{: #vcda-adding-deleting-private-ep}

Where VMware Cloud Director Availability (VCDA) is enabled, {{site.data.keyword.cloud}} provides a public endpoint for each cloud zone in the region that has at least one resource pool. Public endpoints are read only and cannot be deleted. You can request instance endpoints for private connections for an extra charge.

For multitenant virtual data centers, both public and private endpoints are available by default, read-only, and cannot be deleted.
{: note}

## Procedure to add a private connection
{: #vcda-adding-deleting-private-ep-proc-add}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click a Cloud Director site instance.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. On the **Instance endpoints** tab, click **Add private endpoint +**.
5. On the **Request instance endpoint** panel, select the zone and enter the subnets to allowlist for access to the private endpoint.
6. Review the estimated cost, review and accept the terms, and click **Request endpoint**.

## Procedure to delete a private connection from an instance endpoint zone
{: #vcda-adding-deleting-private-ep-proc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click a Cloud Director site instance.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. On the **Instance endpoints** tab, locate the private instance endpoint to delete.
5. Click the overflow menu and click **Delete endpoint**.

## Related links
{: #vcda-delete-adding-links}

* [Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
