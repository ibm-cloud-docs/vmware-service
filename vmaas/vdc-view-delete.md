---

copyright:

  years: 2022, 2023

lastupdated: "2023-08-02"

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
2. In the **{{site.data.keyword.vmware-service_short}}** table, ensure that the **Virtual data centers** tab is selected.
3. Review the VDCs information:  name, location, Cloud Director site, and status.
4. Click the VDC name to view details.

Click **VMware console** to access the service and to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view the VDC details
{: #vdc-view-delete-details}

You can view the VDC details through the Cloud Director site details page.

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab.
2. In the **Cloud director sites** table, expand the Cloud Director site row to view the list of VDCs that are provisioned for that instance.
3. In the **Virtual data centers** table, review the VDC name, provider VDC (PVDC) name, network edge, and status.
4. Click a VDC name to review the complete summary of VDC details.
5. On the **Summary** tab, review the following information:

   * The VDC name, resource group, site, and provider VDC (PVDC) name.
   * The creation date, network edge type, and the globally unique ID of the VDC. This ID can be helpful if you need to open an IBM Support ticket.
   * The 6 public IP addresses that are assigned to the VDC. The IP addresses can be assigned to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses.

6. Use the toggle to either enable or disable fast provisioning.

## Procedure to delete VDCs
{: #vdc-view-delete-delete}

You can delete VDCs from your single-tenant Cloud Director site.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, ensure that the **Virtual data centers** tab is selected.
3. Locate the VDC to delete and click **Delete**.
4. Confirm that you want to delete.

## Related links
{: #vdc-view-delete-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Accessing the VMware Cloud Director console](/docs/vmware-service?topic=vmware-service-accessing-vcd-console)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
