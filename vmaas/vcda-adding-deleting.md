---

copyright:

  years: 2023, 2024

lastupdated: "2024-11-26"

keywords: add vcda, delete vcda, vcda adding, vcda remove, VMware Cloud Director Availability

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting VCDA
{: #vcda-adding-deleting}

You can add the VMware Cloud Director Availability (VCDA) service to your Cloud Director site instance as part of the {{site.data.keyword.vmware-service_full}} order and to existing Cloud Director site instances.

You can delete the service from your instance if you no longer need the service.

VCDA is installed in all virtual data centers (VDCs) for the {{site.data.keyword.vcf-aas-full}} instance. For example, if the instance has resource pools in Dallas 10 and Dallas 12, then VCDA is installed in both of the VDCs in the resource pool clusters and takes CPU and RAM resources from the resource pool clusters and hosts.

## Procedure to add VMware Cloud Director Availability to {{site.data.keyword.vcf-aas}} instances
{: #vcda-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click **Add service**.
5. In the **Add-on services** panel, toggle VMware Cloud Director Availability on.
6. Review the new cost, select the confirmation checkboxes, and click **Add**.

## Procedure to delete VMware Cloud Director Availability from {{site.data.keyword.vcf-aas}} instances
{: #vcda-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click the vertical overflow menu in the VMware Cloud Director Availability service panel and click **Delete service**.
5. In the **Delete add-on service** window, review the considerations, and enter **VMware Cloud Director Availability** to confirm that you want to delete the service from your instance. Click **Delete**.

## Related links
{: #vcda-adding-deleting-links}

* [Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Adding capacity to single-tenant Cloud Director sites with VCDA](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting private instance endpoints with VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
