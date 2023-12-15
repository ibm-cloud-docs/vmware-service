---

copyright:

  years: 2023

lastupdated: "2023-11-20"

keywords: view instance, virtual data center instances, virtual data center view, view virtual data center

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.vmware-service_short}} virtual data centers
{: #tenant-viewing-vdc}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} virtual data centers (VDCs) that are provisioned in your account.

When you no longer need them, you can delete the VDCs that are provisioned in your account.

## Procedure to view a summary of virtual data centers
{: #tenant-viewing-vdc-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab to view a summary of the VDCs that are provisioned.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | VMwaaS type | The consumption model for the VDC: Single-tenant or Multitenant. |
   | Location | The region where the VDC is deployed. |
   | Cloud Director site | The name of the site where the VDC is deployed. |
   | Status | The status of the provisioned VDC. |
   {: caption="Table 1. Virtual data center summary" caption-side="bottom"}

   Click **VMware console** to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view details for a virtual data center
{: #tenant-viewing-vdc-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click a VDC name.
2. On the **Summary** tab, review the virtual data center details.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | Cloud Director Site | The name of the site where the VDC is deployed. Click the name to access site details. |
   | Provider VDC | The name of the provider virtual data center (PVDC) for the VDC. Click the name to access PVDC details. |
   | Created | The date and time that the VDC was created. |
   | Location | The region where the VDC is deployed. |
   | Network edge type | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | ID | The globally unique ID of the VDC. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Public IPs | The 6 public IP addresses that are assigned to the VDC. The IP addresses can be assigned to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses. |
   | Fast provisioning | Use the toggle to either enable or disable fast provisioning for the VDC. |
   {: caption="Table 2. Virtual data center details" caption-side="bottom"}

3. On the **Add-on services** tab, click **Veeam backups** to open the Self-Service Backup Portal.

   You can enable the Veeam® Backup and Replication service through the Cloud Director site details page if the service is not installed.
   {: note}

## Procedure to delete a virtual data center
{: #tenant-viewing-vdc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click the VDC that you want to delete.
3. Click the **Actions...** menu, and then click **Delete instance**.
4. Confirm that you want to delete the instance.

   The status of the VDC is changed to **Deleting**. When the VDC is deleted successfully, the components are released, and the status is changed to **Deleted**.

Alternatively, you can click the delete icon that is located in the VDC row of the **Virtual data centers** summary table.
{: fast-path}

## Related links
{: #tenant-viewing-vdc-links}

* [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Adding and deleting capacity](/docs/vmware-service?topic=vmware-service-capacity-adding-deleting)
* [Adding and deleting Veeam Backup and Replication](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
