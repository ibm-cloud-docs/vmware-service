---

copyright:

  years: 2023

lastupdated: "2023-11-13"

keywords: migrate endpoints, migrate, vcda migration

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Migrating workloads to {{site.data.keyword.vmware-service_short}}
{: #vcda-migrating}

Use VMware Cloud Director Availability (VCDA) to migrate your vCenter virtual machine (VM) workloads from on-premises and VMware vCenter Server® environments to {{site.data.keyword.vmware-service_full}}.

## Before you begin
{: #vcda-migrating-prereq}

Complete the following prerequisites before you migrate your VM workload.

### Install VCDA on-premises in VMware vCenter Server
{: #vcda-migrating-prereq-vmaas-onprem}

Before you configure public or private endpoints, you must install VCDA on-premises in VMware vCenter Server.

The following steps outline a validated process. Many different configurations work.
{: note}

1. From VMware Customer Connect, download the **VMware Cloud Director Availability On-premises Appliance** ``.ova`` file and upload it to your jump server. Ensure that you download the ``.ovf`` file.
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
      * Select the destination compute resource. It is recommended to install the VCDA On-premises Appliance in the same cluster or compute resource where vCenter Server is installed.
   4. For the **Review details** tab, verify all of the configuration details.
   5. For the **License agreements** tab, review and accept the license agreements.
   6. For the **Configuration** tab, select **On-Premises to Cloud Director Replication Appliance**.
   7. Complete the following configuration for the **Select storage** tab.
      * Select **Encrypt the virtual machine** and **Datastore Default** for the thin provision drop-down menu.
      * Select the management share or workload share datastore option from the table. It is recommended that you use the same storage where vCenter Server is installed.
   8. For the **Select networks** tab, select the management network. The management network is the same network as the vCenter Server VM.
   9. Complete the following configuration for the **Customize template** tab.
      * For **Root password**, enter your root password.
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

### Configure the public endpoint with VCDA
{: #vcda-migrating-prereq-vmaas-public-ep}

1. From the VCDA IP address, use the root password to log in. You are asked to change your password.
2. From the **Getting Started** tab, click **Run the initial setup wizard**.
3. From the **Initial Setup** window, complete the following configurations.
   1. Complete the following configuration for the **Lookup Service** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Lookup Service Address**, enter the Fully Qualified Domain Names(FQDN) of the vCenter/PSC of vCenter Server.
      * For **SSO Admin Username**, enter the username of the vCenter of vCenter Server.
      * For **Password**, enter the password of the vCenter of vCenter Server.
   2. Complete the following configuration for the **Site Details** tab.
      * For **Site name**, enter the unique name for your installation.
   3. Complete the following configuration for the **Cloud Service Details** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Public Service Endpoint address**, enter the public service endpoint URL from the **Instance endpoints** tab for your {{site.data.keyword.vmware-service_short}} site. For more information, see [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing).
      * For **Organization Admin**, enter the Organization Administrator user credentials. You must create the credentials in VMware Cloud Director for {{site.data.keyword.vmware-service_short}}.
      * For **Organization Password**, enter the Organization Administrator password.
   4. Review the configuration on the **Ready To Complete** tab and click **Finish**.

### Configure the private endpoint with VCDA
{: #vcda-migrating-prereq-vmaas-private-ep}

1. Log in to the On-premises VCDA console.
2. Click **Settings**. Then, expand the **Network** section and click **Static routes**.
3. Click **ADD** and add a new static route to route the subnet of the private endpoint CSE IP address to the VCDA IP address.
4. On the **Settings** page, click **Repair** to update the pairing to private.
5. Click **Next**
6. From the **Update Pairing** window, complete the following configurations.
   1. Complete the following configuration for the **Site Details** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Lookup Service Address**, enter the Fully Qualified Domain Names(FQDN) of the vCenter/PSC of vCenter Server.
      * For **SSO Admin Username**, enter the username of the vCenter of vCenter Server.
      * For **Password**, enter the password of the vCenter of vCenter Server.
   2. Complete the following configuration for the **Cloud Service Details** tab. After you complete the configuration, click **NEXT**, then **ACCEPT** to accept the configuration.
      * For **Public Service Endpoint address**, enter the private service endpoint URL from the **Instance endpoints** tab for your {{site.data.keyword.vmware-service_short}} site. For more information, see [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing).
      * For **Organization Admin**, enter the Organization Administrator user credentials. You must create the credentials in VMware Cloud Director for {{site.data.keyword.vmware-service_short}}.
      * For **Organization Password**, enter the Organization Administrator password.
   4. Review the configuration on the **Ready To Complete** tab and click **Finish**.

## Procedure to migrate workloads to {{site.data.keyword.vmware-service_short}}
{: #vcda-migrating-procedure}

After you enable your public or private connection, migrate your VM to {{site.data.keyword.vmware-service_short}}.

Ensure that the VM is powered on from vCenter Server.
{: important}

1. From the VMware console, click the **More** drop-down menu to select the VMware Cloud Director Availability instance to migrate.
2. From the VMware Cloud Director Availability console, click **Incoming Replications**.
3. Click **ALL ACTIONS > New migration**.
4. Select the following options in the **New Incoming Migration** window.
   * For **Source VMs**, select the VM to migrate from the **Source site** drop-down and click **NEXT**.
   * For **Destination VDC and Storage policy**, select the target VDC to migrate the VM to and click **NEXT**.
   * For **Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The source VM is configured and then synchronized to the Cloud Director site.

5. Scroll to the bottom of the **vApp/VM** column to locate the replicated VM. The replication is complete when the **Last changed** column moves from *Synchronizing* to the date and time of the replication.
6. When the replication is complete, ensure that the newly replicated VM is selected and click **ALL ACTIONS > Migrate** to begin the migration.
7. Select the following options from the **Migrate** window.
   * For **Migrate Settings**, keep the default options and click **NEXT**.
   * For **Ready to complete**, review the settings and click **FINISH**.

   The VMware Cloud Director Availability service copies the runtime data from the source VM to the destination VM. When the replication is complete, the migrated VM powers on in the Cloud Director site and powers off in the vCenter Server instance. The migration is complete when the **Last changed** column moves from *Migrate* to the date and time of the migration.

8. Click the destination virtual data center name to verify the migration. Click **Compute > Virtual Machines** to view the VM. The migration is successful if the VM is powered on.

### Known issues and workarounds
{: #vcda-migrating-procedure-issues}

From the **Incoming replications** table, the migrated VM doesn’t start synchronizing and synchronization stays at 0%.

1. Log in to the on-premises VMware Cloud Director Availability console.
2. Click **Settings** and expand **Network**. Click **Static routes**.
3. Click **ADD** to add a new static route. For the destination and gateway, use the primary subnet for the hosts and virtual server instances for your vCenter Server instance.
4. Click **APPLY** and the VM synchronizes.

## Related links
{: #vcda-migrating-links}

* [Installing and configuring the On-Premises to Cloud Director Replication Appliance](https://docs.vmware.com/en/VMware-Cloud-Director-Availability/4.6/VMware-Cloud-Director-Availability-Install-Config-Upgrade-On-Prem/GUID-7B6E4E1E-92D5-4D84-A7FD-44B0824815DF.html){: external}
* [Viewing VMware Cloud Director Availability details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding migration capacity](/docs/vmware-service?topic=vmware-service-vcda-capacity-adding)
* [Adding and deleting a private instance endpoint](/docs/vmware-service?topic=vmware-service-vcda-migrating)
