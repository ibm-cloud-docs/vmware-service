---

subcollection: vmware-service
copyright:
  years: 2023, 2024
lastupdated: "2024-11-06"

content-type: tutorial
services: vmware-service
account-plan: paid
completion-time: 30m


---

{{site.data.keyword.attribute-definition-list}}
{:video: .video}

# Migrating workloads from an on-premises vCenter environment to {{site.data.keyword.vcf-aas}}
{: #vcda-migrating-onprem}
{: toc-content-type="tutorial"}
{: toc-services="vmware-service"}
{: toc-completion-time="30m"}

You can use VMware Cloud Director Availability (VCDA) to migrate your vCenter virtual machine (VM) workloads from on-premises and {{site.data.keyword.vcf-classic}} environments to {{site.data.keyword.vmware-service_full}}. Find out how to migrate vApp and virtual machine (VM) workloads from any self-managed vCenter environment to {{site.data.keyword.vcf-aas-full}} in the following video.

![Migrate workloads from any Self-Managed vCenter to {{site.data.keyword.vcf-aas}}](https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/1773841/uiconf_id/27941801/entry_id/1_vrb1m547?wid=_1773841&iframeembed=true&entry_id=1_vrb1m547){: video output="iframe" data-script="none" id="mediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

Some documentation, including, but not limited to, tutorials, solutions architectures, solution guides, videos, and diagrams might still be using the old offering names. This information will be gradually updated to the new offering names in future releases.
{: note}

## Objectives
{: #vcda-migrating-onprem-objectives}

In this tutorial, you learn how to install the VCDA on-premises appliance in a self-managed vCenter environment, configure a public or a private endpoint with a {{site.data.keyword.vcf-aas}} VCDA installation, and migrate your vCenter workloads to {{site.data.keyword.vcf-aas}}.

## Before you begin
{: #vcda-migrating-onprem-prereqs}

The VCDA service is optionally included in your {{site.data.keyword.vcf-aas}} Cloud Director site order at no charge.

This tutorial requires:

* An {{site.data.keyword.cloud_notm}} [billable account](/docs/account?topic=account-accounts).
* Required user permissions. Ensure that your user account has sufficient permissions [to create and manage {{site.data.keyword.vcf-aas}} resources](/docs/vmware-service?topic=vmware-service-getting-started).
* [A preprovisioned {{site.data.keyword.vcf-aas}} Cloud Director site](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering).
* [The VCDA service is installed on your Cloud Director site instance](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting).
* An existing vCenter cluster.
* A free VMware® by Broadcom account.

## Install VCDA on-premises appliance in a self-managed vCenter
{: #vcda-migrating-onprem-vcs}
{: step}

Before you configure public or private endpoints, you must install VCDA on-premises in a self-managed vCenter.

The following steps outline a validated process. Many different configurations work.
{: note}

1. Download the **VMware Cloud Director Availability On-premises Appliance** ``.ova`` file to a server that has a network connection to the self-managed vCenter.
   1. [Log in](https://support.broadcom.com/group/ecx/productfiles?subFamily=VMware%20Cloud%20Director%20Availability&displayGroup=Standard&release=4.7.1&os=&servicePk=203331&language=EN){: external} to VMware by Broadcom or create a free account.
   2. Click the **Drivers and Tools** tab.
   3. Download **VMware Cloud Director Availability On-premises Appliance**.

   Entitlements are not required for the VMware Cloud Director Availability On-premises Appliance. 
   {: note}

2. Log in to VMware vCenter Server and navigate to the cluster name.
3. Right-click the cluster name and click **Deploy OVF Template...**.
4. From the **Deploy OVF Template** window, complete the following configurations. After you complete the configuration for each tab, click **NEXT** to move to the next tab.
   1. Complete the following configuration for the **Select an OVF template** tab.
      * Select **Local file**.
      * Select the ``.ovf`` file and click **UPLOAD FILES**.
   2. Complete the following configuration for the **Select a name and folder** tab.
      * Enter a unique name for the installation. It is recommended to use a VM name that helps to identify VCDA.
      * Select the default folder for the VM.
   3. Complete the following configuration for the **Select a compute resource** tab.
      * Select the destination compute resource. It is recommended to install the VCDA on-premises appliance in the same cluster or compute resource where vCenter Server is installed.
   4. For the **Review details** tab, verify all of the configuration details.
   5. For the **License agreements** tab, review and accept the license agreements.
   6. For the **Configuration** tab, select **On-Premises to Cloud Director Replication Appliance**.
   7. Complete the following configuration for the **Select storage** tab.
      * Select **Encrypt the virtual machine** and **Datastore Default** for the thin provision drop-down menu.
      * Select the management share or workload share datastore option from the table. It is recommended that you use the same storage where vCenter Server is installed.
   8. For the **Select networks** tab, select the management network. The management network is the same network as the vCenter Server VM.
   9. Complete the following configuration for the **Customize template** tab.
      * For **Root password**, set the root password that is used for the first log in to the on-premises VCDA appliance.
      * Select **Enable SSH**.
      * For **NTP Server**, enter the AD/DNS IP addresses from vCenter Server.
      * For **Hostname**, enter any valid hostname.
      * For **Address**, enter the service TO uplink3 that is under Portable subnet for the instance management from vCenter Server.
      * For **Gateway**, enter the Service TO uplink1 virtual IP address.
      * For **MTU (bytes)**, enter the maximum transmission unit in bytes.
      * For **DNS servers**, enter the AD/DNS IP addresses from vCenter Server.
      * For **Search Domains**, enter the root domain of vCenter Server.
   10. For the **Ready to complete** tab, review your selections and click **FINISH**.

      The VCDA on-premises deployment to VMware vCenter Server begins. When the deployment is complete, the new folder that you created is available under the vCenter Server cluster.
5. From the installation folder, navigate to the VM and click the **Power On** icon.
6. When the VM is powered on, navigate to the newly installed VCDA IP address.

## Configure the endpoint with VCDA
{: #vcda-migrating-onprem-ep}
{: step}

For this step, use either the [Configure the public endpoint with VCDA](#vcda-migrating-onprem-public-ep) steps or the [Configure the private endpoint with VCDA](#vcda-migrating-onprem-private-ep) steps.

The private networking endpoint is more secure and provides more consistent performance over the public endpoint. The private endpoint has a monthly cost and the public endpoint is included in your order.

### Configure the public endpoint with VCDA
{: #vcda-migrating-onprem-public-ep}

1. From the VCDA IP address, use the root password that you provided during the VCDA on-premises appliance installation to log in. You are asked to change your password.
2. From the **Getting Started** tab, click **Run the initial setup wizard**.
3. From the **Initial Setup** window, complete the following configurations.
   1. Complete the following configuration for the **Lookup Service** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Lookup Service Address**, enter the Fully Qualified Domain Names(FQDN) of the vCenter/PSC of vCenter Server.
      * For **SSO Admin Username**, enter the username of the vCenter of vCenter Server.
      * For **Password**, enter the password of the vCenter of vCenter Server.
   2. Complete the following configuration for the **Site Details** tab.
      * For **Site name**, enter the unique name for your installation.
   3. Complete the following configuration for the **Cloud Service Details** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Public Service Endpoint address**, enter the public replication endpoint URL from the **Instance endpoints** tab for your {{site.data.keyword.vcf-aas}} site. For more information, see [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing).
      * For **Organization Admin**, enter a local Organization Administrator user credential. You must create the credentials in VMware Cloud Director for {{site.data.keyword.vcf-aas}}. You must use a local VMware Cloud Director administrator account. IAM SSO credentials are not supported.

      If you use the ``admin`` user ID, you must include the Organization ID. For example, ``admin@8db98de2-7735-41f1-a487-64fcaefde250``.
      {: note}

      * For **Organization Password**, enter the Organization Administrator password.
   4. Review the configuration on the **Ready To Complete** tab and click **Finish**.

### Configure the private endpoint with VCDA
{: #vcda-migrating-onprem-private-ep}
{: step}

1. Log in to the On-premises VCDA console.
2. Click **Settings**. Then, expand the **Network** section and click **Static routes**.
3. Click **ADD** and add a new static route to route the subnet of the private endpoint CSE IP address to the VCDA IP address.
4. From the **Getting Started** tab, click **Run the initial setup wizard**.
5. From the **Initial Setup** window, complete the following configurations.
   1. Complete the following configuration for the **Lookup Service** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Lookup Service Address**, enter the Fully Qualified Domain Names(FQDN) of the vCenter/PSC of vCenter Server.
      * For **SSO Admin Username**, enter the username of the vCenter of vCenter Server.
      * For **Password**, enter the password of the vCenter of vCenter Server.
   2. Complete the following configuration for the **Site Details** tab.
      * For **Site name**, enter the unique name for your installation.
   3. Complete the following configuration for the **Cloud Service Details** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Public Service Endpoint address**, enter the public replication endpoint URL from the **Instance endpoints** tab for your {{site.data.keyword.vcf-aas}} site. For more information, see [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing).
      * For **Organization Admin**, enter a local Organization Administrator user credential. You must create the credentials in VMware Cloud Director for {{site.data.keyword.vcf-aas}}. You must use a local VMware Cloud Director administrator account. IAM SSO credentials are not supported.
      * For **Organization Password**, enter the Organization Administrator password.
   4. Review the configuration on the **Ready To Complete** tab and click **Finish**.

## Migrate VMware vCenter workloads to {{site.data.keyword.vcf-aas}}
{: #vcda-migrating-onprem-migrate}
{: step}

After you enable your public or private connection, migrate your VM to {{site.data.keyword.vcf-aas}}.

Ensure that the VM is powered on from vCenter Server.
{: important}

1. From the VMware console, click the **More** drop-down menu to select the VCDA instance to migrate.
2. From the VCDA console, click **Incoming Replications**.
3. Click **ALL ACTIONS > New migration**.
4. Select the following options in the **New Incoming Migration** window.
   * For **Source VMs**, select the VM to migrate from the **Source site** drop-down and click **NEXT**.
   * For **Destination VDC and Storage policy**, select the target VDC to migrate the VM to and click **NEXT**.
   * For **Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The source VM is configured and then synchronized to the Cloud Director site. The replication is complete when the **Last changed** column moves from *Synchronizing* to the date and time of the replication.

5. When the replication is complete, ensure that the newly replicated VM is selected and click **ALL ACTIONS > Migrate** to begin the migration.
6. Select the following options from the **Migrate** window.
   * For **Migrate Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VCDA service copies the runtime data from the source VM to the destination VM. When the replication is complete, the migrated VM powers on in the Cloud Director site and powers off in the vCenter Server instance. The migration is complete when the **Recovery state** column moves from *Not started* to *Failed-Over*.

7. Click the destination virtual data center name to verify the migration. Click **Compute > Virtual Machines** to view the VM.
8. After the migration is complete, delete the failed-over migration. Click **ALL ACTIONS > Delete replication**.

The migration metadata is deleted. Deleting the replication does not delete the source or the destination VMs.
{: note}

## Known issues and workarounds
{: #vcda-migrating-onprem-issues}

From the **Incoming replications** table, the migrated VM doesn’t start synchronizing and synchronization stays at 0%.

The VCDA appliance cannot reach the ESXi hosts. If no VMkernel adapter has the “vSphere Replication” and “vSphere Replication NFC” assigned services, VCDA uses the Management VMkernel adapter. For the VMkernal adapter that is used, VCDA must reach this IP address on the ESXi host for replication.

To resolve, add static routes on the VCDA appliance.

1. Log in to the on-premises VCDA console.
2. Click **Settings** and expand **Network**. Click **Static routes**.
3. Click **ADD** to add a new static route. For the destination and gateway, use the primary subnet for the hosts and virtual server instances for your vCenter Server instance.
4. Click **APPLY** and the VM synchronizes.
