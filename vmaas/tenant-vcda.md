---

copyright:

  years:  2023, 2024

lastupdated: "2024-04-16"

keywords: VMware Cloud Director Availability, VMware Cloud Director Availability installation

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Director Availability for {{site.data.keyword.vcf-aas}} overview
{: #tenant-vcda}

Deliver simple, secure, and cost-effective onboarding and migration support with VMware Cloud Director Availability (VCDA).

{{site.data.keyword.vmware-service_full}} with VCDA supports several migration scenarios:
* Migrate vCenter virtual machine (VM) workloads from on-premises and vCenter Server environments to {{site.data.keyword.vcf-aas-full}} over the public or private {{site.data.keyword.IBM}} network.
* Migrate workloads from VMware Shared to {{site.data.keyword.vcf-aas}}.
* Migrate workloads from {{site.data.keyword.vcf-aas}} single-tenant and multitenant instances to another {{site.data.keyword.vcf-aas}} instance.

The VCDA service is included by default in all multitenant virtual data centers (VDCs) and optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge.

{{site.data.keyword.IBM_notm}} provides public instance endpoints with VCDA. Endpoints are used to access the VCDA web interface and also to migrate workloads. You can request new endpoints for private connections for an additional charge. With private endpoints, you can migrate workloads into {{site.data.keyword.vcf-aas}} using the {{site.data.keyword.cloud_notm}} private network to improve consistency and security. Cloud-to-cloud migrations from both VMware Shared and from {{site.data.keyword.vcf-aas}} to {{site.data.keyword.vcf-aas}} are over the private network.

## Accessing the VMware Cloud Director Availability console
{: #tenant-vcda-portal}

When you are ready to complete your migration, you can access the VCDA console from the **Add-on services** tab of a virtual data center instance details page for both multitenant and single-tenant instances.

### Procedure to access the VMware Cloud Director Availability console from the instance
{: #tenant-vcda-portal-proc-access}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. Click the **Virtual data center** tab. Then, click the instance name.
3. Click the **Add-on services** tab on the instance details page.
4. On the **VMware Cloud Director Availability** service, click **Open VCDA**.
6. Use a user with the Organization Administrator role to log in to the VCDA console. A newly provisioned virtual data center's **admin** user has the role by default.

Alternatively, you can access the VCDA console through the Cloud Director site details page. For more information, see [Viewing migration details](/docs/vmware-service?topic=vmware-service-vcda-viewing).

## Related links
{: #tenant-vcda-related}

* [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding migration capacity](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
* [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
