---

copyright:

  years: 2022, 2025

lastupdated: "2025-02-06"

keywords: view instance, cloud director site instances, cloud director site view, view cloud director site

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites
{: #tenant-viewing-sites}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} Cloud Director sites that are provisioned in your account.

When you no longer need them, you can delete the Cloud Director sites that are provisioned in your account.

You cannot delete a single-tenant Cloud Director site instance if it still has virtual data centers (VDCs) in it. Before you delete your Cloud Director site, ensure that all VDC instances in the site are deleted.

For multitenant instances, you can delete only VDCs. The Cloud Director site is automatically deleted when the last VDC in the region is deleted.

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
   | Location | The name of the data center where the site is deployed. |
   | Network connection | Identifies the connection type: public and private or private only. |
   | Transit gateway | The status of the Transit Gateway connection. |
   {: caption="Virtual data center summary" caption-side="bottom"}

   Click the **Delete** icon on the VDC row to delete the VDC from the Cloud Director site.

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
   {: caption="Cloud Director site details" caption-side="bottom"}

   If a recommended service is not already installed for the site, you can click the service link to install or enable the service for your instance.

3. On the **Networking** tab, review the type of management and workload connectivity. For private-only management connectivity, you can view and edit the allowlisted subnets.

4. On the **Infrastructure** tab, review details for each resource pool provisioned for the site. Click the resource pool tab in the right panel to open details.

     * Click the **Clusters** tab to view all clusters that are deployed on the resource pool and to view cluster details: name, total cores and RAM, host units, storage type, and status. Expand the cluster to view host and storage details.
     * Click the **Virtual data centers** tab to view all VDCs deployed on the resource pool and to view VDC details: name, edge type, fast provisioning, and status. Click a VDC name to review complete VDC details.
     * Click the **Network edges** tab to view the edges that are deployed on the resource pool and to view edge details: type, quantity, vCPU, and RAM.

6. On the **Add-on services** tab, review your options for available services.
     * Click **Add service** to install a service.
     * Click the overflow menu to delete a service.
     * If Veeam® Backup is installed, click **Veeam backups** to open the Self-Service Backup Portal.
     * Expand the **VMware Cloud Director Availability** service to see details and available options for the service. For more information, see [VMware Cloud Director Availability for {{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda).

## Procedure to delete a Cloud Director site
{: #tenant-viewing-site-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab, then click the site that you want to delete.
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
