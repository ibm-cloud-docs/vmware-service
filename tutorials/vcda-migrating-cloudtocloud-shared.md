---
subcollection: vmware-service
copyright:
  years: 2023, 2024
lastupdated: "2024-09-13"

content-type: tutorial
services: vmware-service
account-plan: paid
completion-time: 30m

---
{{site.data.keyword.attribute-definition-list}}
{:video: .video}

# Migrating VMware Shared workloads to {{site.data.keyword.vcf-aas}} with cloud-to-cloud connections
{: #vcda-migrating-cloudtocloud-shared}
{: toc-content-type="tutorial"}
{: toc-services="vmware-service"}
{: toc-completion-time="30m"}

VMware Shared is no longer be available for new deployments. Existing instances will continue to be supported until 15 January 2025. Ensure that you migrate all your VMware Shared resources to [{{site.data.keyword.vmware-service_full}}](/docs/vmware-service) by 15 January 2025. For more information, see [End of Support for VMware Shared deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vmware-shared).
{: deprecated}

You can use VMware Cloud Director Availability (VCDA) to migrate your workloads from an {{site.data.keyword.vmwaresolutions_full}} Shared virtual data center (VDC) to {{site.data.keyword.vcf-aas-full}}. Find out how to migrate vAPP and virtual machine (VM) workloads in the following video.

![Migrate workloads from IBM Cloud VMWare Shared to {{site.data.keyword.vcf-aas}}](https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/1773841/uiconf_id/27941801/entry_id/1_hycjbyi0?wid=_1773841&iframeembed=true&entry_id=1_hycjbyi0){: video output="iframe" data-script="none" id="mediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

## Objectives
{: #vcda-migrating-cloudtocloud-shared-objectives}

In this tutorial, you learn how to migrate vApps and VMs between your {{site.data.keyword.vcf-aas}} instance and VMware Shared instances.

Pairings are automatically created to the closest geographical VMware Shared region when you install VCDA on a {{site.data.keyword.vcf-aas}} instance. Migrations between VMware Shared and {{site.data.keyword.vcf-aas}} require a pairing between the two offerings. The following pairings are supported and created automatically.
* {{site.data.keyword.vcf-aas}} DAL region pairs with VMware Shared DAL region
* {{site.data.keyword.vcf-aas}} WDC region pairs with VMware Shared DAL region
* {{site.data.keyword.vcf-aas}} FRA region pairs with VMware Shared FRA region

## Before you begin
{: #vcda-migrating-cloudtocloud-shared-prereqs}

The VCDA service is optionally included in your {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge and is always included in multitenant {{site.data.keyword.vcf-aas}} VDCs.

This tutorial requires:

* An {{site.data.keyword.cloud_notm}} [billable account](/docs/account?topic=account-accounts).
* Required user permissions. Ensure that your user account has sufficient permissions [to create and manage {{site.data.keyword.vcf-aas}} resources](/docs/vmware-service?topic=vmware-service-getting-started).
* A VMware Shared virtual data center instance to migrate.
* [A provisioned {{site.data.keyword.vcf-aas}} VDC](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering). You can use either a multitenant VDC or a single-tenant Cloud Director site with a VDC.
* [The VCDA service is installed in your {{site.data.keyword.vcf-aas}} Cloud Director site instance](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting). VCDA is installed by default in all multitenant VDCs.
* The {{site.data.keyword.vcf-aas}} instance must have networks created before you migrate.
* If the VMs to migrate have connectivity to the IBM private network or the public internet, verify that the following edge requirements are met.
   * The {{site.data.keyword.vcf-aas}} network(s) are connected to the edge.
   * The {{site.data.keyword.vcf-aas}} VDC is created with an edge.
   * The {{site.data.keyword.vcf-aas}} VDC edge has NATs and firewalls configured.

   You may need to update allowlists or DNS entries with new public IP addresses that result from the migration.
   {: note}

## Create a VMware Shared pairing
{: #vcda-migrating-cloudtocloud-shared-pairing}
{: step}

1. From the VMware Solutions console, install VCDA on a {{site.data.keyword.vcf-aas}} single-tenant instance. For more information, see [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting#vcda-adding-deleting-add-proc).

   VCDA is preinstalled on multitenant instances.
   {: note}

2. Create a VDC on the VMware Shared instance to migrate. For more information, see [Ordering virtual data centers](/docs/vmwaresolutions?topic=vmwaresolutions-shared_ordering).
3. From the VMware Shared VDC details page, click **vCloud Director console**. For more information, see [Viewing site and virtual data center details](/docs/vmwaresolutions?topic=vmwaresolutions-shared_viewing-vdc-details).
4. A local organization administrator user is required for VCDA migrations. To create a local user, click the **Administration** menu from the Director console.
5. Expand **Access Control** and click **Users**.
6. From the **Users** page, click **NEW** to create a new local user. Include the following information for the new user profile:
   * A password.
   * For **Role**, select **Organization Administrator**.
   * For **Organization ID**, enter the organization ID for the VDC. You can locate the ID in the vCloud Director console URL. For example, *test_xxxx*.
7. Click **FINISH** to create the new user.
8. Click **Data Centers** and locate the VDC.
9. From the VDC, create a virtual machine (VM).

## Migrate your VM through the VMware Shared pairing
{: #vcda-migrating-cloudtocloud-shared-migrate-pairing}
{: step}

1. From the VMware Solutions console, go to the {{site.data.keyword.vmware-service_short}} instance with VCDA installed and click **VMware console**.
2. From the VMware console, click **More > Availability ``datacenter_name``**. For example, *Availability (sdirw360t04vcda)*.
3. From the left panel, click **Peer Sites** to review the VMware Shared peer site options.
4. Select the peer site for the VMware Shared workload to migrate and click **LOGIN**. The peer site name is the VMware Shared organization. To find the VMWare Shared organization name, log in to the Cloud Director user interface in VMware Shared and click a VDC. At the top of the web page, you can find the organization ID.
5. Provide the following login credentials for the peer site and click **LOGIN**.
   * For **Username**, use the local user ID that you created in the VMWare console for the VMware Shared pairing.
   * For **Password**, use the local password ID that you created in the VMWare console for the VMware Shared pairing.

The login is successful when the green checkmark icon displays in the **Management Session** column for the peer site.

## Replicate and migrate the VM to {{site.data.keyword.vcf-aas}}
{: #vcda-migrating-cloudtocloud-shared-migrate}
{: step}

Ensure that the VMware Shared VM is powered on from the VMware console.
{: important}

1. From the VMware console, click **Incoming Replications**.
2. From the **Incoming Replications** page, click **ALL ACTIONS > New migration**.
3. Provide the login credentials for the peer site and click **LOGIN**.
4. Select the following options in the **New Incoming Migration** window.
   * For **Source VMs and vApps**:
      1. From the **Source organization** menu, select the organization ID that you located in the URL when you created the user ID for the VMware Shared pairing.
      2. Select the VM to replicate and click **NEXT**.
   * For **Destination VDC and Storage policy**, select the target VDC to migrate the VM to and click **NEXT**.
   * For **Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VM is first configured and then synchronized. The replication is complete when the **Last changed** column moves from *Synchronizing* to the date and time of the replication.

5. When the replication is complete, ensure that the newly replicated VM is selected and click **ALL ACTIONS > Migrate** to begin the migration.
6. Select the following options from the **Migrate** window:
   * For **Migrate Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VCDA service copies the runtime data from the source VM to the destination VM. When the replication is complete, the migrated VM powers on in the Cloud Director site and powers off in the VMware Shared instance. The migration is complete when the **Recovery state** column moves from *Not started* to *Failed-Over*.

7. Click the destination virtual data center name to verify the migration. Click **Compute > Virtual Machines** to view the VM.
8. After the migration is complete, delete the failed-over migration. Click **ALL ACTIONS > Delete replication**.

The migration metadata is deleted. Deleting the replication does not delete the source or the destination VMs.
{: note}
