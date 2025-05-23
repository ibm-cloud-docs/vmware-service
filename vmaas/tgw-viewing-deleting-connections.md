---

copyright:

  years: 2024, 2025

lastupdated: "2025-04-01"

keywords: view connection, interconnectivity, transit gateway, delete connection

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.tg_short}} connections
{: #tgw-viewing-deleting-connections}

You can view the status of your {{site.data.keyword.tg_full}} connection and delete the connection group if you no longer need it.

## Procedure to view {{site.data.keyword.tg_short}} connection details
{: #tgw-viewing-connections-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the virtual data center name.
3. Click the **Interconnectivity** tab to open the {{site.data.keyword.tg_short}} connections page.
4. Expand the **{{site.data.keyword.tg_short}} ID** to review the connection group details.
5. Expand each connection group to review the details and status of each associated GRE tunnel.

   | Status | Description |
   |:---- |:----------- |
   | Not connected | The {{site.data.keyword.tg_short}} connection group is not connected to {{site.data.keyword.tg_short}}. You must connect all six GRE tunnels to {{site.data.keyword.tg_short}} to complete the connection. |
   | Generating connection values | Automation is running to generate the connection values. Refresh the page to confirm that the values are generated before you request to create the Transit Gateway connections. |
   | Pending | The status remains pending until you attach all six GRE tunnels to {{site.data.keyword.tg_short}}. |
   | Creating | All six GRE tunnels are attached to {{site.data.keyword.tg_short}} and the connection group is being created. |
   | Attached | The GRE tunnel is attached to {{site.data.keyword.tg_short}} and the connection group is created. |
   | Disconnected | A stand-alone GRE tunnel was deleted from your {{site.data.keyword.tg_short}}. Click **Reattach connection to {{site.data.keyword.tg_short}}** to return to the {{site.data.keyword.tg_short}} console to reattach the connection. |
   | Deleting | The connection group and associated GRE tunnels are being deleted. |
   {: caption="Connection group and unbound GRE tunnel connection statuses " caption-side="bottom"}

## Procedure to delete a {{site.data.keyword.tg_short}} connection
{: #tgw-deleting-connections-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the virtual data center name.
3. Click the **Interconnectivity** tab to open the {{site.data.keyword.tg_short}} connections page.
4. On the {{site.data.keyword.tg_short}} connections page, click the overflow menu for the connection group and click **Delete connection group**.
5. In the **Delete connection group** pane, enter the {{site.data.keyword.tg_short}} ID to confirm the deletion. Then, click **Delete**.

The **Deleting** status displays for the connection group and all associated GRE tunnels. When the deletion is complete, the connection group no longer displays on the {{site.data.keyword.tg_short}} connections page.

## Related links
{: #tgw-viewing-deleting-connections-links}

* [Using {{site.data.keyword.tg_short}} to interconnect {{site.data.keyword.vcf-aas}} with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections)
* [Getting help and support for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-support)
