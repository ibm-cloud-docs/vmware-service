---

copyright:

  years: 2022, 2023

lastupdated: "2023-06-06"

keywords: view virtual data center, view virtual data centers, vdc view, delete vdc, virtual data center delete

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting virtual data centers
{: #vdc-view-delete}

View the summary and detailed information of the virtual data centers (VDCs) in your {{site.data.keyword.vmware-service_full}} instance.

## Procedure to view a summary of VDCs
{: #vdc-view-delete-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, expand a {{site.data.keyword.vmware-service_short}} instance row to view the list of VDCs that are provisioned for that instance.
3. Review the VDCs information: VDC name, provider VDC name, network edge, and VDC status.

## Procedure to view the VDC details
{: #vdc-view-delete-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, expand a {{site.data.keyword.vmware-service_short}} instance row to view the list of VDCs that are provisioned for that instance.
2. In the **Virtual data centers** table, click a VDC name.
3. On the **Summary** tab, review the following information:

   * The VDC name, resource group, site, and provider VDC (PVDC) name.
   * The creation date, network edge type, and the globally unique ID of the VDC. This ID can be helpful if you need to open an IBM Support ticket.
   * The 6 public IP addresses that are assigned to the VDC. The IP addresses can be assigned to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses.

4. To reset the administrator password, click **Reset on site level**.
5. Use the toggle to either enable or disable fast provisioning.
6. To access the service and to create and manage networking and workloads, click **VMware Cloud Director console**. For more information, see [Accessing the VMware Cloud Director console](/docs/vmware-service?topic=vmware-service-accessing-vcd-console).

## Procedure to delete VDCs
{: #vdc-view-delete-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, expand a {{site.data.keyword.vmware-service_short}} instance row to view the list of VDCs that are provisioned for that instance.
3. To delete the VDC, click the overflow menu and select **Delete**.

## Related links
{: #vdc-view-delete-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Accessing the VMware Cloud Director console](/docs/vmware-service?topic=vmware-service-accessing-vcd-console)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
