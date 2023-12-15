---
subcollection: vmware-service
copyright:
  years: 2023
lastupdated: "2023-12-13"

content-type: tutorial
services: vmware-service
account-plan: paid
completion-time: 30m

---
{{site.data.keyword.attribute-definition-list}}

# Migrating VMware Shared workloads to {{site.data.keyword.vmware-service_short}} with cloud-to-cloud connections
{: #vcda-migrating-cloudtocloud-shared}
{: toc-content-type="tutorial"}
{: toc-services="vmware-service"}
{: toc-completion-time="30m"}

You can use VMware Cloud Director Availability (VCDA) to migrate your workloads from a {{site.data.keyword.vmwaresolutions_full}} Shared virtual data center (VDC) to {{site.data.keyword.vmware-service_short}}.

## Objectives
{: #vcda-migrating-cloudtocloud-shared-objectives}

In this tutorial, you learn how to migrate virtual machines (VMs) and vApps between your {{site.data.keyword.vmware-service_short}} instance and VMware Shared instances.

Pairings are automatically created to the closest geographical VMware Shared region when you install VCDA on a {{site.data.keyword.vmware-service_short}} instance. Migrations between VMware Shared and {{site.data.keyword.vmware-service_short}} require a pairing between the two offerings. The following pairings are supported and created automatically.
* {{site.data.keyword.vmware-service_short}} DAL region pairs with VMware Shared DAL region
* {{site.data.keyword.vmware-service_short}} WDC region pairs with VMware Shared DAL region
* {{site.data.keyword.vmware-service_short}} FRA region pairs with VMware Shared FRA region

## Before you begin
{: #vcda-migrating-cloudtocloud-shared-prereqs}

The VCDA service is optionally included in your {{site.data.keyword.vmware-service_short}} Cloud Director site order at no charge and is always included in multitenant {{site.data.keyword.vmware-service_short}} VDCs.

This tutorial requires:

* An {{site.data.keyword.cloud_notm}} [billable account](/docs/account?topic=account-accounts).
* Required user permissions. Ensure that your user account has sufficient permissions [to create and manage {{site.data.keyword.vmware-service_short}} resources](/docs/vmware-service?topic=vmware-service-getting-started).
* [A preprovisioned {{site.data.keyword.vmware-service_short}} Cloud Director site](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering).
* [The VCDA service is installed on your Cloud Director site instance](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting).
* A {{site.data.keyword.vmwaresolutions_short}} Shared instance to migrate.

## Create a VMware Shared pairing
{: #vcda-migrating-cloudtocloud-shared-pairing}
{: step}

1. From the VMware Solutions console, install VCDA on a {{site.data.keyword.vmware-service_short}} single-tenant instance. For more information, see [Adding and deleting VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting#vcda-adding-deleting-add-proc).

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

1. From the VMware Solutions console, navigate to the {{site.data.keyword.vmware-service_short}} instance with VCDA installed and click **VMware console**.
2. From the VMware console, click **More > Availability (<datacenter_name>)**. For example, *Availability (sdirw360t04vcda)*.
3. From the left panel, click **Peer Sites** to review the VMware Shared peer site options.
4. Select the peer site for the VMware Shared workload to migrate and click **LOGIN**. The peer site name is the VMware Shared organization. To find the VMWare Shared organization name, log in to the Cloud Director user interface in VMware Shared and click a VDC. At the top of the web page, you can find the organization ID.
5. Provide the following login credentials for the peer site and click **LOGIN**.
   * For **Username**, use the local user ID that you created in the VMWare console for the VMware Shared pairing.
   * For **Password**, use the local password ID that you created in the VMWare console for the VMware Shared pairing.

The login is successful when the green checkmark icon displays in the **Management Session** column for the peer site.

## Replicate and migrate the VM to {{site.data.keyword.vmware-service_short}}
{: #vcda-migrating-cloudtocloud-shared-migrate}
{: step}

Ensure that the VMware Shared VM is powered on from the VMware console.
{: important}

1. From the VMware console, click **Incoming Replications**.
2. From the **Incoming Replications** page, click **ALL ACTIONS > New migration**.
3. Provide the login credentials for the peer site and click **LOGIN**.
4. Select the following options in the **New Incoming Migration** window.
   * For **Source VMs and vApps**:
   1. From the **Source organization** drop-down menu, select the organization ID that you located in the URL when you created the user ID for the VMware Shared pairing.
   2. Select the VM to replicate and click **NEXT**.
   * For **Destination VDC and Storage policy**, select the target VDC to migrate the VM to and click **NEXT**.
   * For **Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VM is first configured and then synchronized. The replication is complete when the **Last changed** column moves from *Synchronizing* to the date and time of the replication.

5. When the replication is complete, ensure that the newly replicated VM is selected and click **ALL ACTIONS > Migrate** to begin the migration.
6. Select the following options from the **Migrate** window.
   * For **Migrate Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VCDA service copies the runtime data from the source VM to the destination VM. When the replication is complete, the migrated VM powers on in the Cloud Director site and powers off in the VMware Shared instance. The migration is complete when the **Recovery state** column moves from *Not started* to *Failed-Over*.

7. Click the destination virtual data center name to verify the migration. Click **Compute > Virtual Machines** to view the VM.
8. After the migration is complete, delete the failed-over migration. Click **ALL ACTIONS > Delete replication**.

The migration metadata is deleted. Deleting the replication does not delete the source or the destination VMs.
{: note}
