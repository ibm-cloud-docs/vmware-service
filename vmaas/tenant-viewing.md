---

copyright:

  years: 2022, 2023

lastupdated: "2022-10-18"

keywords: view tenant instance, single tenant instances, view instance, single tenant view

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing {{site.data.keyword.vmware-service_short}} single-tenant instances
{: #tenant-viewing}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} single-tenant instances that are provisioned in your account.

## Procedure to view a summary of {{site.data.keyword.vmware-service_short}} single-tenant instances
{: #tenant-viewing-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click either the **Virtual data centers** tab or the **Cloud director sites** tab to view the list of instances that are provisioned.
3. Review the summary to locate the **VMwaas type** of *Siingle-tenant*.
   * For virtual data centers, review the VDC name, {{site.data.keyword.vmware-service_short}} type, location, Cloud Director site name, and status of the provisioned instance.
   * For Cloud Director sites, review the site name, {{site.data.keyword.vmware-service_short}} type, location, and status of the provisioned instance.

Click **VMware console** to access the service and to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view details for single-tenant virtual data center instances
{: #tenant-viewing-vdc-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click a single-tenant instance name.
2. On the **Summary** tab, review the virtual data center details.

   The following actions are available on the **Summary** tab.
   * Access the Cloud Director site details page.
   * Access the PVDC details page.
   * Toggle fast provisioning off or on.

3. On the **Add-on services** tab, click **Veeam backups** to open the Self-Service Backup Portal.

   You can enable the Veeam® Backup and Replication service through the Cloud Director site details page if the service is not installed.
   {: note}

## Procedure to view details for single-tenant Cloud Director site instances
{: #tenant-viewing-site-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab. Then, click a single-tenant instance name.
2. On the **Summary** tab, review the Cloud Director site details.

   If the Veeam Backup and Replication service is not already enabled for the site, you can click **Enable Veeam Backup and Replication** to provision the service for your instance.

3. On the **Infrastructure** tab, review infrastructure details for each provisioned provider virtual data center (PVDC).
     * Click the **Clusters** tab to view all clusters that are deployed on the PVDC including cluster details such as total cores and RAM, host units, storage type, and cluster status. Expand the cluster to view host and storage details.
     * Click the **Virtual data centers** tab to view all VDCs deployed on the PVDC including VDC name, edge type, fast provisioning, and VDC status. Click a VDC name to review VDC details.
     * Click the **Network edges** tab to view the edges that are deployed on the PVDC including type, quantity, vCPU, and RAM.
4. On the **Add-on services** tab, review your options for available services.
     * Enable or delete Veeam Backup and Replication.
     * Click **Veeam backups** to open the Self-Service Backup Portal.

## Related links
{: #tenant-viewing-links}

* [Adding a provider virtual data centers](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting)
* [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting)
* [Adding and deleting hosts](/docs/vmware-service?topic=vmware-service-host-adding-deleting)
* [Adding and deleting storage](/docs/vmware-service?topic=vmware-service-storage-adding-deleting)
