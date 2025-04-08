---

copyright:

  years: 2023, 2025

lastupdated: "2025-04-04"

keywords: view instance, virtual data center instances, virtual data center view, view virtual data center

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers
{: #tenant-viewing-vdc}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} virtual data centers (VDCs) that are provisioned in your account.

When you no longer need them, you can delete the VDCs that are provisioned in your account.

Click the **Switch view mode** icon in the **Create** panel to open the original resource list summary view.
{: note}

## Procedure to view a summary of virtual data centers
{: #tenant-viewing-vdc-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, review the summary of VDCs that are provisioned for the Cloud Director site.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | Status | The status of the provisioned VDC. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   | Location | The data center where the VDC is deployed. For regional high availability VDCs, the primary and secondary data centers are displayed. |
   | Network connection | Identifies the connection type: public and private or private only. |
   | Transit gateway | The status of the Transit Gateway connection. |
   {: caption="Virtual data center summary" caption-side="bottom"}

## Procedure to view details for a virtual data center
{: #tenant-viewing-vdc-details}

1. In the **Virtual data centers** table for the Cloud Director site, click the VDC name to review the VDC details.
2. On the **Summary** tab, review the virtual data center details.

   | Item | Description |
   |:---- |:----------- |
   | Cloud Director instance | The name of the site where the VDC is deployed. Click **View** to access site details. |
   | Network location | The primary and secondary network location where the VDC is deployed for a highly available network edge. Click **Swap primary and secondary**  to change the locations. |
   | Name | The name of the VDC. |
   | Resource group | The resource grouping for user access to assignments in the Cloud user account. |
   | Region | The region where the VDC is deployed. |
   | Compute location | The data center where the VDC is deployed. Both data centers display for a stretched resource pool. |
   | Creation time | The date and time that the VDC was created. |
   | ID | The globally unique ID of the VDC. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Network edge type | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | Network connection | The type of network connection of either private only or both public and private. |
   | Fast provisioning | Use the toggle to either turn fast provisioning on or off for the VDC. |
   | Public IPs or Private IPs| The public or private IP addresses that are assigned to the VDC. For public IP addresses, you can assign them to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   {: class="simple-tab-table"}
   {: caption="Virtual data center details - single-tenant" caption-side="bottom"}
   {: #table1}
   {: tab-title="Single-tenant instances"}
   {: tab-group="vdc details"}

   | Item | Description |
   |:---- |:----------- |
   | Consumption limit | The current vCPU and RAM consumption limits. Click **Modify limit** to turn consumption limits on or off, and to increase or decrease limits. |
   | Pricing plan | The pricing plan for the virtual data center. Pricing plans are either on-demand or reserved. |
   | Cloud Director instance | The name of the instance where the VDC is deployed. Click **View site** to access site details. |
   | Network location | The primary and secondary network location where the VDC is deployed for a highly available network edge. Click **Swap primary and secondary**  to change the locations. |
   | Name | The name of the VDC. |
   | Resource group | The resource grouping for user access to assignments in the Cloud user account. |
   | Region | The region where the VDC is deployed. |
   | Compute location | The data center where the VDC is deployed. Both data centers display for a stretched resource pool. |
   | Creation time | The date and time that the VDC was created. |
   | ID | The globally unique ID of the VDC. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Network edge type | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | Network connection | The type of network connection of either private only or both public and private. |
   | Fast provisioning | Use the toggle to either turn fast provisioning on or off for the VDC. |
   | Public IPs or Private IPs | The public or private IP addresses that are assigned to the VDC. For public IP addresses, you can assign them to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses. |
   | Regional high availability | Identifies type of high availability for the VDC, if any. |
   {: class="simple-tab-table"}
   {: caption="Virtual data center details - multitenant" caption-side="bottom"}
   {: #table2}
   {: tab-title="Multitenant instances"}
   {: tab-group="vdc details"}

   For VDCs deployed after VMware Cloud Director™ IP Spaces availability, IP addresses are managed and viewed through the VMware Cloud Director tenant portal. For more information, see [Allocating public IP addresses for NAT rules and for VPNs](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-allocating-ips).

3. On the **Add-on services** tab, review the available services.

   * Click **Open VCDA** to open the VMware Cloud Director Availability (VCDA) Console.
   * Click **Veeam backups** to open the Self-Service Backup Portal.

   You can enable the Veeam® Backup and VCDA services through the Cloud Director site details page if the services are not installed.
   {: note}

4. On the **Interconnectivity** tab, see details for Transit Gateway connections. For more information, see [Viewing and deleting Transit Gateway connections](/docs/vmware-service?topic=vmware-service-tgw-viewing-deleting-connections).

Click **VMware console** to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to delete a virtual data center
{: #tenant-viewing-vdc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. In the **Virtual data center** table, click the VDC name that you want to delete.
3. Click the **Actions** menu, and then click **Delete instance**.
4. Confirm that you want to delete the instance.

   The status of the VDC is changed to **Deleting**. The components are released when the VDC is deleted successfully.

Alternatively, you can click the delete icon that is located in the VDC row of the **Virtual data centers** summary table.
{: fast-path}

## Related links
{: #tenant-viewing-vdc-links}

* [{{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Adding and deleting capacity](/docs/vmware-service?topic=vmware-service-capacity-adding-deleting)
* [Adding and deleting Veeam Backup](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
