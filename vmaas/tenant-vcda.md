---

copyright:

  years:  2023, 2025

lastupdated: "2025-09-16"

keywords: VMware Cloud Director Availability, VMware Cloud Director Availability migration

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA
{: #tenant-vcda}

Deliver simple, secure, and cost-effective migration support with VMware Cloud Director Availability (VCDA).

Both migration and disaster recovery support are available when you install the VCDA service. For more information about disaster recovery configurations, see [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda-dr).

The VCDA service is included by default in all multitenant virtual data centers (VDCs) and optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge. For a VCDA *disaster recovery* configuration, a monthly charge is incurred per protected virtual machine (VM).

{{site.data.keyword.vmware-service_full}} with VCDA supports several migration scenarios:
* Migrate vCenter virtual machine workloads from on-premises and vCenter Server environments to {{site.data.keyword.vcf-aas-full}} over the public or private {{site.data.keyword.IBM}} network
* Migrate workloads from {{site.data.keyword.vcf-aas}} single-tenant and multitenant instances to another {{site.data.keyword.vcf-aas}} instance
* Migrate workloads from VMware Cloud Director™ instances to {{site.data.keyword.vcf-aas}} environments

You must open an IBM Support ticket to request a VCDA connection from your VMware Cloud Director instance to {{site.data.keyword.vcf-aas}}. For more information, see [Connecting VMware Cloud Director instances to VCF as a Service](/docs/vmware-service?topic=vmware-service-vcda-vdc-connect).
{: note}

{{site.data.keyword.IBM_notm}} provides public instance endpoints with VCDA. Endpoints are used to access the VCDA web interface and also to migrate workloads. You can request new endpoints for private connections for an additional charge. With private endpoints, you can migrate workloads into {{site.data.keyword.vcf-aas}} by using the {{site.data.keyword.cloud_notm}} private network to improve consistency and security. Cloud-to-cloud migrations from {{site.data.keyword.vcf-aas}} to {{site.data.keyword.vcf-aas}} are over the private network.

## Accessing the VMware Cloud Director Availability console
{: #tenant-vcda-portal}

When you are ready to complete your migration or data recovery configuration, you can access the VCDA console from the **Add-on services** tab of a virtual data center instance details page for both multitenant and single-tenant instances.

### Procedure to access the VMware Cloud Director Availability console from the instance
{: #tenant-vcda-portal-proc-access}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the virtual data center name.
3. Click the **Add-on services** tab in the instance details page.
4. In the **VMware Cloud Director Availability** section, click **Open VCDA**.
6. Use a user with the Organization Administrator role to log in to the VCDA console. A newly provisioned virtual data center's **admin** user has the role by default.

Alternatively, you can access the VCDA console through the Cloud Director site details page. For more information, see [Viewing migration details](/docs/vmware-service?topic=vmware-service-vcda-viewing).

## Related links
{: #tenant-vcda-related}

* [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding capacity to single-tenant Cloud Director sites with VCDA](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting private instance endpoints with VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
* [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
