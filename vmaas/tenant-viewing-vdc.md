---

copyright:

  years: 2023, 2024

lastupdated: "2024-08-27"

keywords: view instance, virtual data center instances, virtual data center view, view virtual data center

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers
{: #tenant-viewing-vdc}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} virtual data centers (VDCs) that are provisioned in your account.

When you no longer need them, you can delete the VDCs that are provisioned in your account.

## Procedure to view a summary of virtual data centers
{: #tenant-viewing-vdc-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab to view a summary of the VDCs that are provisioned.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | VCFaaS type | The consumption model for the VDC: Single-tenant or Multitenant. |
   | Location | The data center where the VDC is deployed. |
   | Network connection | Identifies the connection type: public and private or private only. |
   | Transit Gateway | The status of the Transit Gateway connection. |
   | Cloud Director instance | The name of the site where the VDC is deployed. |
   | Status | The status of the provisioned VDC. |
   {: caption="Table 1. Virtual data center summary" caption-side="bottom"}

   Click **VMware console** to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view details for a virtual data center
{: #tenant-viewing-vdc-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click a VDC name.
2. On the **Summary** tab, review the virtual data center details.

   | Item | Description |
   |:---- |:----------- |
   | Cloud Director instance | The name of the instance where the VDC is deployed. Click **View site** to access site details. |
   | Resource pool | The name of the resource pool for the VDC. Click **View resource pool** to access resource pool details. |
   | Name | The name of the VDC. |
   | Region | The region where the VDC is deployed. |
   | Creation time | The date and time that the VDC was created. |
   | ID | The globally unique ID of the VDC. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Public IPs or Private IPs| The 6 public or private IP addresses that are assigned to the VDC. For public IP addresses, you can assign them to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses. |
   | Network edge type | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | Network connection | The type of network connection of either private only or both public and private. |
   | Fast provisioning | Use the toggle to either enable or disable fast provisioning for the VDC. |
   {: class="simple-tab-table"}
   {: caption="Table 2. Virtual data center details - single-tenant" caption-side="bottom"}
   {: #table1}
   {: tab-title="Single-tenant instances"}
   {: tab-group="vdc details"}

   | Item | Description |
   |:---- |:----------- |
   | vCPU limit and RAM limit | The current vCPU and RAM consumption limits. Click **Modify limit** to enable or disable limits and increase or decrease limits. |
   | Pricing plan | The pricing plan for the virtual data center. Pricing plans are either on-demand or reserved. |
   | Cloud Director instance | The name of the instance where the VDC is deployed. Click **View site** to access site details. |
   | Data center | The data center where the VDC is deployed. |
   | Name | The name of the VDC. |
   | Region | The region where the VDC is deployed. |
   | Creation time | The date and time that the VDC was created. |
   | ID | The globally unique ID of the VDC. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Public IPs or Private IPs | The 6 public or private IP addresses that are assigned to the VDC. For public IP addresses, you can assign them to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses. |
   | Network edge type | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | Network connection | The type of network connection of either private only or both public and private. |
   | Fast provisioning | Use the toggle to either enable or disable fast provisioning for the VDC. |
   {: class="simple-tab-table"}
   {: caption="Table 2. Virtual data center details - multitenant" caption-side="bottom"}
   {: #table2}
   {: tab-title="Multitenant instances"}
   {: tab-group="vdc details"}

3. On the **Add-on services** tab, review the available services.

   * Click **Open VCDA** to open the VMware Cloud Director Availability (VCDA) Console.
   * Click **Veeam backups** to open the Self-Service Backup Portal.

   You can enable the Veeam® Backup and VCDA services through the Cloud Director site details page if the services are not installed.
   {: note}

4. For a description of the **Interconnectivity** tab, see [Viewing and deleting Transit Gateway connections](/docs/vmware-service?topic=vmware-service-tgw-viewing-deleting-connections).

## Procedure to delete a virtual data center
{: #tenant-viewing-vdc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click the VDC that you want to delete.
3. Click the **Actions...** menu, and then click **Delete instance**.
4. Confirm that you want to delete the instance.

   The status of the VDC is changed to **Deleting**. When the VDC is deleted successfully, the components are released, and the status is changed to **Deleted**.

Alternatively, you can click the delete icon that is located in the VDC row of the **Virtual data centers** summary table.
{: fast-path}

## Related links
{: #tenant-viewing-vdc-links}

* [{{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Adding and deleting capacity](/docs/vmware-service?topic=vmware-service-capacity-adding-deleting)
* [Adding and deleting Veeam Backup](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
