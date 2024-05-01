---

copyright:

  years: 2023, 2024

lastupdated: "2024-04-23"

keywords: migrate endpoints, migrate, vcda migration

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Installing VMware Cloud Director Availability on-premises in VMware vCenter Server
{: #vcda-migrating}

Complete the following steps to install VMware Cloud Director Availability (VCDA) on-premises in VMware vCenter Server®.

The following steps outline a validated process. Many different configurations work.
{: note}

1. From VMware Customer Connect, download the **VMware Cloud Director Availability On-premises Appliance** ``.ova`` file to a server that has a network connection to the vCenter Server.

   Entitlements are not required for the VMware Cloud Director Availability On-premises Appliance. For more information about creating a VMware Customer Connect account, see [VMware Customer Connect](https://customerconnect.vmware.com/account-registration). {: external}
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
      * Select the destination compute resource. It is recommended to install the VCDA On-premises Appliance in the same cluster or compute resource where vCenter Server is installed.
   4. For the **Review details** tab, verify all of the configuration details.
   5. For the **License agreements** tab, review and accept the license agreements.
   6. For the **Configuration** tab, select **On-Premises to Cloud Director Replication Appliance**.
   7. Complete the following configuration for the **Select storage** tab.
      * Select **Encrypt the virtual machine** and **Datastore Default** for the thin provision drop-down menu.
      * Select the management share or workload share datastore option from the table. It is recommended that you use the same storage where vCenter Server is installed.
   8. For the **Select networks** tab, select the management network. The management network is the same network as the vCenter Server VM.
   9. Complete the following configuration for the **Customize template** tab.
      * For **Root password**, set the root password used for the first log in to the on-premises VCDA appliance.
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

## Related links
{: #vcda-migrating-links}

* [Installing and configuring the On-Premises to Cloud Director Replication Appliance](https://docs.vmware.com/en/VMware-Cloud-Director-Availability/4.6/VMware-Cloud-Director-Availability-Install-Config-Upgrade-On-Prem/GUID-7B6E4E1E-92D5-4D84-A7FD-44B0824815DF.html){: external}
* [Migrating workloads from on-premises and vCenter Server environments to {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vcda-migrating-onprem)
