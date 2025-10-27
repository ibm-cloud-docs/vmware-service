---

copyright:

  years: 2022, 2025

lastupdated: "2025-10-24"

keywords: view instance, cloud director site instances, cloud director site view, view cloud director site

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites
{: #tenant-viewing-sites}

{{site.data.content.vms-deprecated-note}}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} Cloud Director sites that are provisioned in your account.

When you no longer need them, you can delete the Cloud Director sites that are provisioned in your account.

You cannot delete a single-tenant Cloud Director site instance if it still has virtual data centers (VDCs) in it. Before you delete your Cloud Director site, ensure that all VDC instances in the site are deleted.

For multitenant instances, you can delete only VDCs. The Cloud Director site is automatically deleted when the last VDC in the region is deleted.

Click the **Switch view mode** icon next to **Create** to open the original resource list summary view.
{: note}

## Procedure to view a summary of Cloud Director sites
{: #tenant-viewing-sites-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, view the summary of Cloud Director sites and the VDCs that are provisioned for each site. Each site summary includes the following information.

   * The name and status of the provisioned site.
   * The consumption model for the site, Single-tenant or Multitenant, and the region where the site is deployed.
   * The services that are installed and available for the VDCs to use.
   * Available actions for the site.
   
   Click **VMware console** to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).
   
   Click the **Delete** icon to delete the Cloud Director site. You cannot delete an IBM managed multitenant site.

3. View the summary of VDCs that are provisioned for the site.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | Status | The status of the VDC. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   | Location | The name of the data center where the site is deployed. For regional high availability VDCs, the primary and secondary data centers are displayed. |
   | Network connection | Identifies the connection type: public and private or private only. |
   | Transit gateway | The status of the Transit Gateway connection. |
   {: caption="Virtual data center summary" caption-side="bottom"}

   Click the **Delete** icon in the VDC row to delete the VDC from the Cloud Director site.

## Procedure to view details for the Cloud Director site
{: #tenant-viewing-sites-details}

1. Click the Cloud Director site name.
2. On the **Summary** tab, review the site information: the number of resource pools, clusters, VDCs, and network edges that are provisioned for the site. Under **Site details**, review the following details:

   | Item | Description |
   |:---- |:----------- |
   | Infrastructure | The {{site.data.keyword.vcf-aas-full}} offering uses {{site.data.keyword.cloud_notm}} Classic Infrastructure. |
   | Resource group | The resource grouping for user access to assignments in the Cloud user account. |
   | Region | The region where the site is deployed. |
   | VCFaaS type | The consumption model for the site: Single-tenant or Multitenant. |
   | Creation time | The date and time that the site was created. |
   | Billing cycle | The pricing plan for the site. |
   | ID | The globally unique ID of the site. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   | Red Hat activation key | The Red Hat Enterprise Linux activation key that is used to register the Red Hat VM. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   {: caption="Cloud Director site details" caption-side="bottom"}

   If a recommended service is not already installed for the site, you can click the service link to install or enable the service for your instance.

3. On the **Networking** tab, review the type of management and workload connectivity. Under **Network edges**, review the following details:

   | Item | Description |
   |:---- |:----------- |
   | Name | The VDC name. |
   | Type | The edge performance type. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   | Location | The name of the data center where the site is deployed. For regional high availability VDCs, the primary and secondary data centers are displayed. |
   | vCPU | The amount of virtual CPU for the VDC. |
   | RAM | The amount of RAM for the VDC. |
   {: caption="Network edge details" caption-side="bottom"}

   Use the search bar to narrow down the network edge list.

4. On the **Resource pool** tab, review details for each resource pool provisioned for the site.

     * The name and status of the resource pool.
     * The type of resource pool: standard or stretched high availability, the data centers where the resource pool is deployed, and if the host is an SAP-certified server.
     * The total computing and vSAN storage capacity of the resource pool.
     * The total NFS storage capacity of the resource pool.
     
   Expand the **Clusters** section to view all clusters that are deployed on the resource pool and to view cluster details.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the cluster. |
   | Status | The status of the cluster. |
   | Profile | The host profile of the cluster. |
   | Total CPU | The total host CPU for the cluster. |
   | Total RAM | The total host RAM for the cluster. |
   | vSAN storage | The amount of vSAN storage space. |
   | NFS storage | The attached NFS storage tier and space. |
   |Host units | The number of hosts for the host profile. |
   {: caption="Cluster details" caption-side="bottom"}

   Click **Actions** to complete the following actions for the cluster:

   * [Edit host quantity](/docs/vmware-service?topic=vmware-service-host-adding-deleting)
   * [Edit NFS storage](/docs/vmware-service?topic=vmware-service-storage-adding-deleting)
   * [View monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
   * [Delete the cluster](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting)

5. On the **Virtual data centers** tab, review details for each VDC provisioned for the site.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | Location | The name of the data center where the site is deployed. For regional high availability VDCs, the primary and secondary data centers are displayed. |
   | Resource pool | The name of the resource pool for the VDC. |
   | Regional high availability | Identifies the type of high availability for the VDC, if any. |
   | Network connection | Identifies the connection type: public and private or private only. Available if you provisioned a network edge with your VDC order. |
   | Transit gateway | The status of the Transit Gateway connection. |
   |Creation time | The date and time that the VDC was created. |
   | Status | The status of the VDC. |
   {: caption="Virtual data center details" caption-side="bottom"}

   Click the VDC name to review the VDC details. For more information, see [Viewing and deleting VCF as a Service virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc#tenant-viewing-vdc-details).

6. On the **Add-on services** tab, review your options for available services.
     * Click **Add service** to install a service.
     * Click the overflow menu to delete a service.
     * If Veeam® Backup is installed, click **Veeam backups** to open the Self-Service Backup Portal. 
     * Expand the **VMware Cloud Director Availability** service to see details and available options for the service. For more information, see [VMware Cloud Director Availability for {{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda).

## Procedure to delete a Cloud Director site
{: #tenant-viewing-site-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name that you want to delete.
3. Click the **Actions** menu, and then click **Delete instance**.
4. Confirm that you want to delete the instance.

   The status of the Cloud Director site is changed to **Deleting**. When the site is deleted successfully, the components are released, and the status is changed to **Deleted**.

Alternatively, you can click the delete icon that is located in the site row of the **Cloud director sites** summary table.
{: fast-path}

## Related links
{: #tenant-viewing-sites-links}

* [Adding resource pools](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting)
* [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting)
* [Adding and deleting Veeam Backup](/docs/vmware-service?topic=vmware-service-veeam-adding-deleting)
* [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
