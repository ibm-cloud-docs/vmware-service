---

copyright:

  years: 2023, 2025

lastupdated: "2025-06-06"

keywords: migrate endpoints, migrate, vcda migration

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Installing VCDA on-premises in VMware vCenter Server
{: #vcda-migrating}

Complete the following steps to install VMware Cloud Director Availability (VCDA) on-premises in VMware vCenter Server®.

The following steps outline a validated process. Many different configurations work.
{: note}

1. Download the **VMware Cloud Director Availability On-premises Appliance** ``.ova`` file to a server that has a network connection to the vCenter Server.
   1. [Log in](https://support.broadcom.com/group/ecx/productfiles?subFamily=VMware%20Cloud%20Director%20Availability&displayGroup=Standard&release=4.7.1&os=&servicePk=203331&language=EN){: external} to VMware® by Broadcom or create a free account.
   2. From the **Cloud** drop-down menu next to the username, select **VMware Cloud Foundation**.
   3. Select **My Downloads** and [Free Software Downloads available HERE](https://support.broadcom.com/group/ecx/free-downloads).{: external}
   4. Click **VMware Cloud Director Availability** and download **VMware Cloud Director Availability On-premises Appliance**.

   Entitlements are not required for the VMware Cloud Director Availability On-premises Appliance.
   {: note}

2. Log in to VMware vCenter Server and navigate to the cluster name.
3. Right-click the cluster name and click **Deploy OVF Template...**.
4. In the **Deploy OVF Template** window, complete the following configurations. After you complete the configuration for each tab, click **NEXT** to move to the next tab.
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
      * For **Root password**, set the root password that is used for the first log into the on-premises VCDA appliance.
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
5. In the installation folder, navigate to the VM and click the **Power On** icon.
6. When the VM is powered on, navigate to the newly installed VCDA IP address.

## Related links
{: #vcda-migrating-links}

* [Migrating workloads from on-premises and vCenter Server environments to {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vcda-migrating-onprem)
