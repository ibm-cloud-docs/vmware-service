---

copyright:

  years: 2023

lastupdated: "2023-11-16"

keywords: add private endpoint, private endpoint adding, VMware Cloud Director Availability

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting private instance endpoints
{: #vcda-adding-deleting-private-ep}

When VMware Cloud Director Availability (VCDA) is enabled, {{site.data.keyword.cloud}} provides a public endpoint for each zone. Public endpoints are read only and cannot be deleted. You can request instance endpoints for private connections for an additional charge.

## Procedure to add a private connection to an instance endpoint zone
{: #vcda-adding-deleting-private-ep-proc-add}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click a single-tenant instance name.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. On the **Instance endpoints** tab, click **Add private endpoint +**.
5. On the **Request instance endpoint** panel, select the zone and enter the subnets for the private endpoint.
6. Click **Request endpoint**.

## Procedure to delete a private connection from an instance endpoint zone
{: #vcda-adding-deleting-private-ep-proc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click a single-tenant instance name.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. On the **Instance endpoints** tab, locate the private instance endpoint to delete.
5. Click the overflow menu and click **Delete endpoint**.

## Related links
{: #vcda-delete-adding-links}

* [VMware Cloud Director Availability for {{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
