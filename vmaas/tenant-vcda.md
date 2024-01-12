---

copyright:

  years:  2023

lastupdated: "2023-12-20"

keywords: VMware Cloud Director Availability, VMware Cloud Director Availability installation

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Director Availability for {{site.data.keyword.vmware-service_short}} overview
{: #tenant-vcda}

Deliver simple, secure, and cost-effective onboarding and migration support with VMware Cloud Director Availability (VCDA).

{{site.data.keyword.vmware-service_full}} with VCDA supports several migration scenarios:
* Migrate vCenter virtual machine (VM) workloads from on-premises and vCenter Server environments to {{site.data.keyword.vmware-service_short}} over the public or private {{site.data.keyword.IBM}} network.
* Migrate workloads from VMware Shared to {{site.data.keyword.vmware-service_short}}.
* Migrate workloads from {{site.data.keyword.vmware-service_short}} single-tenant and multitenant instances to another {{site.data.keyword.vmware-service_short}} instance.

The VCDA service is included by default in all multitenant virtual data centers (VDCs) and optionally included in your single-tenant {{site.data.keyword.vmware-service_short}} Cloud Director site order at no charge.

{{site.data.keyword.IBM_notm}} provides public instance endpoints with VCDA. Endpoints are used to access the VCDA web interface and also to migrate workloads. You can request new endpoints for private connections for an additional charge. With private endpoints, you can migrate workloads into {{site.data.keyword.vmware-service_short}} using the {{site.data.keyword.cloud_notm}} private network to improve consistency and security. Cloud-to-cloud migrations from both VMware Shared and from {{site.data.keyword.vmware-service_short}} to {{site.data.keyword.vmware-service_short}} are over the private network.

## Accessing the VMware Cloud Director Availability console
{: #tenant-vcda-portal}

When you are ready to complete your migration, you can access the VCDA console from the **Add-on services** tab of the Cloud Director site instance details page for both multitenant and single-tenant instances.

### Procedure to access the VMware Cloud Director Availability console from the instance
{: #tenant-vcda-portal-proc-access}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. Click the **Cloud director sites** tab. Then, click the instance name.
3. Click the **Add-on services** tab on the instance details page and expand the **VMware Cloud Director Availability** service.
4. In the **Instance endpoints** table, click the overflow menu for the endpoint to migrate and click **Endpoint details**.
5. Click **Open VCDA**.
6. Use a user with the Organization Administrator role to log in to the VCDA console. A newly provisioned virtual data center's **admin** user has the role by default.

## Related links
{: #tenant-vcda-related}

* [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding migration capacity](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
* [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
