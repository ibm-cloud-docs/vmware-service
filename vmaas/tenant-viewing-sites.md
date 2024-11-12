---

copyright:

  years: 2022, 2024

lastupdated: "2024-11-08"

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

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab to view the summary of sites that are provisioned.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the site. |
   | VCFaaS type | The consumption model for the site: Single-tenant or Multitenant. |
   | Location | The region where the VDC is deployed. |
   | Status | The status of the provisioned site. |
   {: caption="Cloud Director site summary" caption-side="bottom"}

3. Expand the site row to view the summary of VDCs that are provisioned for that site.

   | Item | Description |
   |:---- |:----------- |
   | Name | The name of the VDC. |
   | Resource pool | The name of the resource pool for the VDC. |
   | Network edge | The edge performance type. Available if you provisioned a network edge with your VDC order. |
   | Status | The status of the VDC. |
   {: caption="Virtual data center summary" caption-side="bottom"}

   Click **VMware console** to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view details for the Cloud Director site
{: #tenant-viewing-sites-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab. Then, click the site name.

2. On the **Summary** tab, review the complete summary of Cloud Director site details: the number of resource pools provisioned for the site, the number of VDCs provisioned for the site, the site details, and the recommended services for the site.

   | Item | Description |
   |:---- |:----------- |
   | Infrastructure | The {{site.data.keyword.vcf-aas-full}} offering uses {{site.data.keyword.cloud_notm}} Classic Infrastructure. |
   | Resource group | Resource grouping for user access to assignments in the Cloud user account. |
   | Billing cycle | The pricing plan for the site. |
   | Creation time | The date and time that the site was created. |
   | ID | The globally unique ID of the site. This ID can be helpful to copy if you need to open an IBM Support ticket. |
   {: caption="Cloud Director site details" caption-side="bottom"}

   If a recommended service is not already installed for the site, you can click the service link to install or enable the service for your instance.

3. On the **Networking** tab, review the type of management and workload connectivity. For private-only management connectivity, you can view and edit the allowlisted subnets.
4. On the **Resource pool** tab, review details for each resource pool provisioned for the site. Click the resource pool tab in the right panel to open details.
     * Click the **Clusters** tab to view all clusters that are deployed on the resource pool and to view cluster details: name, total cores and RAM, host units, storage type, and status. Expand the cluster to view host and storage details.
     * Click the **Virtual data centers** tab to view all VDCs deployed on the resource pool and to view VDC details: name, edge type, fast provisioning, and status. Click a VDC name to review complete VDC details.
     * Click the **Network edges** tab to view the edges that are deployed on the resource pool and to view edge details: type, quantity, vCPU, and RAM.
5. On the **Add-on services** tab, review your options for available services.
     * Click **Add service** to install a service.
     * Click the overflow menu to delete a service.
     * If Veeam® Backup is installed, click **Veeam backups** to open the Self-Service Backup Portal.
     * Expand the **VMware Cloud Director Availability** service to see details and available options for the service. For more information, see [VMware Cloud Director Availability for {{site.data.keyword.vcf-aas}} overview](/docs/vmware-service?topic=vmware-service-tenant-vcda).

## Procedure to delete a Cloud Director site
{: #tenant-viewing-site-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab. Then, click the site that you want to delete.
3. Click the **Actions...** menu, and then click **Delete instance**.
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
