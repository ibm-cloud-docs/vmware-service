---

copyright:

  years: 2023

lastupdated: "2023-11-06"

keywords: add vcda, delete vcda, vcda adding, vcda remove, VMware Cloud Director Availability

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting VMware Cloud Director Availability
{: #vcda-adding-deleting}

You can add the VMware Cloud Director Availability (VCDA) service to your Cloud Director site instance as part of the VMWare as a Service order and to existing Cloud Director site instances.

You can delete the service from your instance if you no longer need the service.

VCDA is installed in all virtual data centers (VDCs) for the {{site.data.keyword.vmware-service_short}} instance. For example, if the instance has provider VDCs (PVDCs) in Dallas 10 and Dallas 12, then VCDA is installed in both of the VDCs in the PVDC clusters and takes CPU and RAM resources from the PVDC clusters and hosts.

## Procedure to add VMware Cloud Director Availability to {{site.data.keyword.vmware-service_short}} instances
{: #vcda-adding-deleting-add-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click **Available services**.
5. On the **Add-on services** window, toggle VMware Cloud Director Availability on.
6. Review the new cost, select the confirmation checkboxes, and click **Add**.

## Procedure to delete VMware Cloud Director Availability from {{site.data.keyword.vmware-service_short}} instances
{: #vcda-adding-deleting-delete-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click an instance name.
3. Click the **Add-on services** tab.
4. Click the vertical overflow menu in the VMware Cloud Director Availability service panel and click **Delete service**.
5. In the **Delete add-on service** window, review the considerations, and enter **VMware Cloud Director Availability** to confirm that you want to delete the service from your instance. Click **Delete**.

## Related links
{: #vcda-adding-deleting-links}

* [VMware Cloud Director Availability for {{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Adding migration capacity](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting-private-ep)
