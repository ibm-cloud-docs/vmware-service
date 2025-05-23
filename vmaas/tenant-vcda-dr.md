---

copyright:

  years:  2024, 2025

lastupdated: "2025-05-20"

keywords: VMware Cloud Director Availability, VMware Cloud Director Availability disaster recovery

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA
{: #tenant-vcda-dr}

Deliver simple, secure, and cost-effective disaster recovery support with VMware Cloud Director Availability (VCDA).

Both disaster recovery and migration support are available when you install the VCDA service. For more information about migration scenarios, see [Migrating workloads to VCF as a Service with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda).

The VCDA service is included by default in all multitenant virtual data centers (VDCs) and optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order. For a VCDA *disaster recovery* configuration, a monthly charge is incurred per protected virtual machine (VM).

With the VCDA service, you can replicate workloads from a source {{site.data.keyword.vcf-aas}} environment over to a second {{site.data.keyword.vcf-aas}} environment. Replicating VMware® by Broadcom workloads protects the workloads if a disaster with the source VMware by Broadcom environment where workloads can fail over and run on the second VMware by Broadcom environment. The workload replication frequency is configurable by default to as low as every five minutes. The number of replications to maintain can range from 1 to 24. Optionally, you can open an {{site.data.keyword.cloud_notm}} support ticket to request that replications are reduced down to as low as one minute.

You can create the following disaster recover configurations.
  
* {{site.data.keyword.vcf-aas}} single-tenant or multitenant to {{site.data.keyword.vcf-aas}} single-tenant or multitenant environments
* On-premises to {{site.data.keyword.vcf-aas}} environments
* {{site.data.keyword.vcf-classic}} to {{site.data.keyword.vcf-aas}} environments

For a tutorial on how to create a disaster recovery configuration that uses a {{site.data.keyword.vcf-aas}} single-tenant instance as the primary workload environment and a {{site.data.keyword.vcf-aas}} multitenant instance as the disaster recovery environment, see [Configuring disaster recovery with VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-creating-dr-config).

For more information about installing VCDA on-premises, see [Installing VCDA on-premises in VMware vCenter Server](/docs/vmware-service?topic=vmware-service-vcda-migrating).

## Accessing the VMware Cloud Director Availability console
{: #tenant-vcda-portal-dr}

When you are ready to complete your data recovery configuration, you can access the VCDA console from the **Add-on services** tab of a virtual data center instance details page for both multitenant and single-tenant instances.

### Procedure to access the VMware Cloud Director Availability console from the instance
{: #tenant-vcda-portal-proc-access-dr}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the virtual data center name.
3. Click the **Add-on services** tab in the instance details page.
4. In the **VMware Cloud Director Availability** section, click **Open VCDA**.
6. Use a user with the Organization Administrator role to log in to the VCDA console. A newly provisioned virtual data center's **admin** user has the role by default.

Alternatively, you can access the VCDA console through the Cloud Director site details page. For more information, see [Viewing migration details](/docs/vmware-service?topic=vmware-service-vcda-viewing).

## Related links
{: #tenant-vcda-related-dr}

* [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding and deleting private instance endpoints with VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
* [Creating and deleting {{site.data.keyword.vcf-aas}} pairings with VCDA](/docs/vmware-service?topic=vmware-service-vcda-creating-deleting-vmaas-pairing)
* [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
