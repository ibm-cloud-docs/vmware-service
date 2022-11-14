---

copyright:

  years: 2022

lastupdated: "2022-11-09"

keywords: view virtual data center, view virtual data centers, vdc view

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting virtual data centers
{: #vdc-view-delete}

View the summary and detailed information of the virtual data centers (VDCs) in your {{site.data.keyword.vmware-service_short}} instance.

## Procedure to view a summary of virtual data centers
{: #vdc-view-delete-summary}

1. In the {{site.data.keyword.vmware-service_short}} console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, expand a {{site.data.keyword.vmware-service_short}} instance row.
3. View the list of VDCs that are provisioned for that instance.
4. Review the VDCs information.

## Procedure to view the details of a virtual data center
{: #vdc-view-delete-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click a {{site.data.keyword.vmware-service_short}} instance name.
2. On the **Summary** tab, review the following information:

   * The VDC name, resource group, creation date, and network edge type.
   * The 6 public IP addresses that are assigned to the VDC. The IP addresses can be assigned to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses.
   * The {{site.data.keyword.vmware-service_short}} instance and the cluster that host the VDC.
   * The globally unique ID of the VDC. This ID can be helpful if you need to open an IBM Support ticket.

3. To access the service, and to create and manage networking and workloads, click **VMware Cloud Director console**.
4. Go to [Accessing the VMware Cloud Director Management console](/docs/vmware-service?topic=vmware-service-accessing-vcd-console).

## Procedure to delete virtual data centers
{: #vdc-view-delete-delete}

1. In the {{site.data.keyword.vmware-service_short}} console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, expand a {{site.data.keyword.vmware-service_short}} instance row to view the list of VDCs.
3. To delete the VDC, click the overflow menu and select **Delete**.

## Related links
{: #vdc-view-delete-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Accessing the VMware Cloud Director Management console](/docs/vmware-service?topic=vmware-service-accessing-vcd-console)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
