---

copyright:

  years: 2022, 2023

lastupdated: "2022-10-16"

keywords: view multitenant instance, multitenant instances, view instance, multitenant view

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Viewing {{site.data.keyword.vmware-service_short}} multitenant instances
{: #tenant-viewing-mt}

View the summary and detailed information of the {{site.data.keyword.vmware-service_full}} multitenant instances that are provisioned in your account.

## Procedure to view a summary of multitenant instances
{: #tenant-viewing-mt-summary}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click either the **Virtual data centers** tab or the **Cloud director sites** tab to view the list of instances that are provisioned.
3. Review the summary to locate the **VMwaas type** of *Multitenant*.
   * For virtual data centers, review the VDC name, {{site.data.keyword.vmware-service_short}} type, location, Cloud Director site name, and status of the provisioned instance.
   * For Cloud Director sites, review the site name, {{site.data.keyword.vmware-service_short}} type, location, and status of the provisioned instance.

Click **VMware console** to access the service and to create and manage networking and workloads. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmwaresolutions?topic=vmwaresolutions-iam-integration&interface=ui).

## Procedure to view details for {{site.data.keyword.vmware-service_short}} multitenant virtual data center instances
{: #tenant-viewing-mt-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Virtual data centers** tab. Then, click a multitenant instance name.
2. On the **Summary** tab, review the complete summary of VDC details: consumption limits, name, Cloud Director site name, provider VDC name, network edge type, pricing plan, public IP addresses, creation date and time, and VDC ID.

   The following actions are available on the **Summary** tab.
   * Modify the vCPU and RAM limits.
   * Access the Cloud Director site associated with the VDC.
   * Use the toggle to either enable or disable fast provisioning.
   * Six public IP addresses are assigned to the VDC. The IP addresses can be assigned to support public egress and ingress against the VDC and are not intended to enable VDC creation. It is recommended to use the included VDC firewalls when you are using the public IP addresses.
   * Use the globally unique VDC ID if you need to open an IBM Support ticket.

## Procedure to view details for multitenant Cloud Director site instances
{: #tenant-viewing-mt-site-details}

1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab. Then, click a multitenant instance name.
2. On the **Summary** tab, review the complete summary of Cloud Director site details: region, number of VDCs associated with the site, creation date and time, and recommended services.

   If the Veeam Backup and Replication service is not already installed for the site, you can click **Install Veeam Backup and Replication** to provision the service for your instance.

3. On the **Virtual data centers** tab, review the VDC summary and expand the VDC name to review the VDC details.
4. On the **Add-on services** tab, click **Available services** to install a service or click **Veeam backups** to open the Self-Service Backup Portal.

## Related links
{: #tenant-viewing-mt-links}

* [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview)
* [Adding and deleting capacity](/docs/vmware-service?topic=vmware-service-capacity-adding-deleting)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
