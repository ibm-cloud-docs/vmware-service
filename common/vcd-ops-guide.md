---

copyright:

  years:  2024

lastupdated: "2024-11-01"

keywords: vmware cloud director, rhel, red hat enterprise linux, operating

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Operating VMware Cloud Director
{: #vcd-ops-guide}

## VMware Cloud Director tenant portal overview
{: #vcd-ops-guide-overview}

The VMware Cloud Director™ tenant portal is used for administration of your organization and to create and configure virtual machines (VMs), vApps, and networks within vApps.

You can also configure advanced networking capabilities that are provided by VMware NSX® for vSphere® within a VMware Cloud Director environment. With the tenant portal, you can also create and manage catalogs, vApps, and virtual data center (VDC) templates.

### Roles, permissions, and users
{: #vcd-ops-guide-roles}

To access VMware Cloud Director, use single sign-on with your {{site.data.keyword.cloud_notm}} credentials as the default authentication and authorization mechanism. For a list of the {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) Director tenant portal roles and authorizations that are associated with each role see [Managing IAM access for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui). Organization administrators can create local users that are authenticated by the tenant portal as opposed to IBM Cloud {{site.data.keyword.cloud_notm}} and can also create additional customized roles that can be assigned against local users.

For more information about roles and permissions, see [VMware Cloud Director tenant portal roles and rights](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-754BD24F-63C7-422F-83BC-BFA275CEDA8E.html){: external}.

### Modifying your email settings
{: #vcd-ops-guide-roles-email}

The Organization Administrator must modify email notification settings to the organization SMTP server.

For more information about modifying SMTP server settings, see [Modify your email settings](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-726D40D7-4251-47AD-B945-2030E489165F.html){: external}.

## Catalogs
{: #vcd-ops-guide-catalogs}

A catalog is a container for vApp templates and media files in an organization. Organization administrators and catalog authors can create catalogs in an organization. Catalog contents can be shared with other users or organizations in the {{site.data.keyword.vcf-aas-full}}installation. Or they can be published externally for access by organizations outside the {{site.data.keyword.vcf-aas}} installation.

{{site.data.keyword.vcf-aas}} contains private catalogs, shared catalogs, and externally accessible catalogs. Private catalogs include vApp templates and media files that you can share with other users in the organization. If a system administrator enables catalog-sharing for your organization, you can share an organization catalog to create a catalog accessible to other organizations in the {{site.data.keyword.vcf-aas}} installation.

If a system administrator enables external catalog publishing for your organization, you can publish an organization catalog for access by organizations outside the {{site.data.keyword.vcf-aas}} installation. An organization outside the {{site.data.keyword.vcf-aas}} installation must subscribe to an externally published catalog to access its contents.

Each organization has access to the {{site.data.keyword.vcf-aas}} public catalog. The catalog contains IBM-compliant images that are configured, secured, and ready for use.

### {{site.data.keyword.vcf-aas}} public catalog
{: #vcd-ops-guide-public-cat}

Each organization has access to the {{site.data.keyword.vcf-aas}} public catalog. The catalog contains IBM-compliant images that are configured, secured, and ready for use.

Review the following considerations for {{site.data.keyword.vcf-aas}}:

* Public templates that are configured to services on the IBM private network require an extra configuration step to enable VM access to the IBM Services network. For more information, see [Enabling VM access to {{site.data.keyword.cloud_notm}} Services by using the private network](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-enable-access).
* Public templates require a minimum level of customization to establish the initial administrator password. For more information, see [Changing the guest OS customization properties of a VM](#vcd-ops-guide-customization).

The public catalog contains vApp templates for the following components:

| Image | Version |
|---|---|
| CentOS | 7.x |
| Microsoft® Windows® | 2022 Standard |
| Microsoft Windows | 2019 Standard |
| Microsoft Windows | 2016 Standard |
| Red Hat Enterprise Linux® | 9.3 |
| Red Hat Enterprise Linux | 8.1 |
| Red Hat Enterprise Linux | 7.7 |
| Rocky Linux | 9.4 |
| Rocky Linux | 8.1 |
{: caption="vApp templates" caption-side="bottom"}

#### CentOS and Rocky templates
{: #vcd-ops-guide-public-cat-centos}

The templates that are provided in the public catalog have the following characteristics:

* Latest updates installed
* VMware tools installed
* YUM repository enabled configured to the IBM private network YUM repository
* NTP server that is configured to the IBM private network NTP Server

#### Microsoft Windows templates
{: #vcd-ops-guide-public-cat-windows}

The Microsoft Windows templates that are provided in the public catalog have the following characteristics:
* Latest updates installed
* Windows update enabled configured to the IBM private network Windows update server
* VMware tools installed
* Windows Remote Desktop disabled
* Firewall activated
* Windows Defender activated
* NTP server that is configured to the IBM private network NTP Server
* Windows license configured to activate and receive updates by using the IBM Service Network Microsoft Key Management Server (KMS) and not the internet Microsoft KMS

#### Red Hat Enterprise Linux templates
{: #vcd-ops-guide-public-cat-rhel}

The Red Hat Enterprise Linux (RHEL) templates that are provided in the public catalog have the following characteristics:

* Latest updates installed
* VMware tools installed
* Firewall activated
* NTP server that is configured to the IBM private network servers

After you deploy the VM on the tenant portal, register the Red Hat VM with your RHEL activation key in IBM RHEL Capsule Server. To register the Red Hat VM with your RHEL activation key, you must enable VM access to connect to the IBM service network. For more information, see [Enabling VM access to {{site.data.keyword.cloud_notm}} Services by using the private network](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-enable-access).
{: important}

Complete the following steps to register the Red Hat VM with your RHEL activation key.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
1. From the **Virtual data centers** tab, locate and click the **Cloud Director instance** name.
2. On the **Summary** tab, locate the **Red Hat activation key** in the **Site details** panel and click the **Copy to clipboard** icon.
3. Run the following commands from the Red Hat VM.
     1. `uuid=$(uuidgen)`
     2. `echo {\"dmi.system.uuid\": \"$uuid\"} > /etc/rhsm/facts/uuid_override.facts`
     3. ``cat /etc/rhsm/facts/uuid_override.facts``
       Ensure the contents of the uuid_override.facts contains a generated UUID.
     4. ``subscription-manager register --org="customer" --activationkey="ACTIVATION_KEY" --force``
       Where ``ACTIVATION_KEY`` is the Red Hat activation key that you copied to the clipboard.
       
You can still use another RHEL Capsule Server or a satellite server if you already have an RHEL subscription outside of IBM. Charges for the RHEL license are incurred against RHEL VMs that are running in a VDC.
{: note}

### Defining catalogs and policies
{: #vcd-ops-guide-policies}

To create a catalog, you must have either the **Organizational Administrator** or **Catalog Author** tenant portal role.

For more information about defining catalogs and policies, see [Working with catalogs](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-6424C4A7-EA95-49A0-B673-9DDB971AB566.html){: external}.

### Uploading your media or templates
{: #vcd-ops-guide-customer}

OVF packages can be uploaded to a catalog as a vApp template to make the template available to users. For more information, see [Create a vApp template from an OVF file](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-5EA412C4-179A-42CF-9B30-1B81C23551E6.html){: external}.

Media files, such as ISO disk images and FLP diskette drive images, can be uploaded to a catalog as a media file. For more information, see [Working with media files](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-A7530A4B-F782-4848-90FC-BBDE41E3AE85.html){: external}.

The maximum import size is 750 GB. Large image files or templates might take a long time to upload. For assistance with files larger than 750 GB, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmware-service?topic=vmware-service-support).
{: note}

## Virtual machines
{: #vcd-ops-guide-machines}

When you use the tenant portal, you can create a VM or provision a VM from a template.

For more information, see [Create a standalone virtual machine](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-64CFBEFC-8E3D-49FC-B1BD-16CCE7493544.html){: external}.

### Customizing virtual machine properties
{: #vcd-ops-guide-cust-properties}

You can edit the properties of a VM, including the VM name and description, hardware and network settings, and operating system settings for a guest.

For more information about working with VMs, see [Working with virtual machines](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-DF0C111D-B638-4EC3-B805-CC33994F8D53.html){: external}.

If you use the tenant portal (Guest OS Customization) to change your Windows Administrator password, ensure that you adhere to Windows complexity requirements. If you change the password in the tenant portal without doing so, the password does not work in the Windows VM template.
{: important}

#### Changing the general properties of a virtual machine
{: #vcd-ops-guide-change-properties}

You can change the name, description, storage policy, and other general properties of a VM.

##### Switching between storage properties
{: #vcd-ops-guide-change-properties-storage}

Some disk settings cannot be changed while the VM is powered on. For example, you can increase the disk size while the VM is powered on, but you cannot decrease the disk size unless the VM is powered off. A message displays if you must power off the VM before you modify a disk setting. For more information, see [Power off a virtual machine](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-2323B049-4E36-4510-999E-F2D4A77AC0F9.html){: external}.

For more information about changing a storage policy, see [Change the general properties of a virtual machine](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-FA8C101E-241E-41A5-A3C3-83BDBB4467F1.html#GUID-8301D672-8333-4FD2-B132-2D4A42E11216__GUID-BE9430B7-40F8-43F7-AED4-1080F9E04E34){: external}.

If you must power off the VM before you change a storage policy, power the VM back on after the VM is moved to the new storage policy. For more information, see [Power on a virtual machine](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-33C22124-A610-4C3E-8F40-26CAC570F958.html){: external}.

#### Changing the hardware properties of a virtual machine
{: #vcd-ops-guide-hardware}

You can change the hardware properties of a VM, number of vCPUs, memory, hard disk allocation, and network configuration.

#### Changing the Guest OS Customization properties of a virtual machine
{: #vcd-ops-guide-customization}

Guest OS customization is optional for all platforms. It is required for VMs that must join a Windows domain when the VMs are being powered on.

When you use an IBM template to create the VM, use the **Guest OS Customization** panel to acquire or set the unique password for the OS instance. Ensure that the option **Enable guest customization** is selected and then use one of the **Password Reset** options to establish the initial administrator credential.

For more information, see [Change the guest OS customization properties of a virtual machine](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-FA8C101E-241E-41A5-A3C3-83BDBB4467F1.html#GUID-2B7A04E8-7479-4EE9-99B0-1A46751BE46F__GUID-658C5607-04BA-4BE1-87D3-8553DD2601EE){: external}.

#### Changing the advanced properties of a virtual machine
{: #vcd-ops-guide-advanced}

In the Advanced settings, you can configure the resource allocation settings (shares, reservation, and limit) to determine the amount of virtual CPU (vCPU), memory, and storage resources provided for a VM.

For more information, see [Edit virtual machine properties](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-FA8C101E-241E-41A5-A3C3-83BDBB4467F1.html){: external}.

### Using IBM templates
{: #vcd-ops-guide-ibm-templates}

Password requirements apply if the VM is deployed from the IBM templates that are provided in the public catalog. You must use the initial password that was generated during power-on when you first log in to the VM. You can find this password on the VM details page.

If you use the tenant portal **Password Reset** field to change your Windows Administrator password, ensure that you adhere to Windows complexity requirements. If you change the password in the tenant portal without doing so, the password does not work in the Windows VM template.
{: important}

1. From the **Guest OS Customization** panel, click **EDIT**.
2. From the **Edit Guest Properties** panel, locate the password in the **Specify password** field.
3. After a successful login with the initial password, return to the **Edit Guest Properties** panel to reset the password and log in again with the new password.

## vApps
{: #vcd-ops-guide-vapps}

A vApp consists of one or more VMs that communicate over a network and use resources and services in a VDC. Create the vApp and then add VMs and networks.

You can add VMs and networks to the vApp.

For more information about vApps, see [Working with vApps](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-AC48FB5E-4ADC-4835-AACE-B949B297A147.html){: external}.

## Networking
{: #vcd-ops-guide-networking}

For a complete tutorial on how to create VDC networks inside of your VDC, create VMs to attach to your VDC network, and configure NAT and firewall rules on your edge gateway, see [Configuring a virtual data center in VMware Cloud Foundation as a Service using the VMware Cloud Director Console](/docs/vmware-service?topic=vmware-service-vmware-as-a-service-vdc).

### Enabling VM access to {{site.data.keyword.cloud_notm}} services by using the private network
{: #vcd-ops-guide-enable-access}

You can configure vApps and VMs running inside of the VDC to use the {{site.data.keyword.cloud_notm}} private network to access {{site.data.keyword.cloud_notm}} services. Accessing {{site.data.keyword.cloud_notm}} services through a private network can save on outbound public networking costs and can provide a higher degree of reliability and security. Virtual data centers route to the {{site.data.keyword.cloud_notm}} private network through a VDC service network that is configured as an available external network on the VDC edge.

The following services are available.

| Service | IP address (Endpoint) |
|:------- |:--------------------- |
| Microsoft Windows Update Server | 161.26.4.21 |
| Microsoft Key Management Server | 161.26.96.8, 161.26.96.9 |
| Red Hat Capsule Server | 161.26.96.25 |
| DNS | 161.26.0.10 (`rs1.adn.networklayer.com`) and 161.26.0.11 (`rs2.adn.networklayer.com`) |
| Ubuntu and Debian APT Mirrors | 161.26.0.6 (mirrors.adn.networklayer.com) |
| RHEL and CentOS YUM repo | 161.26.0.6 (mirrors.adn.networklayer.com) |
| NTP | 161.26.0.6 (time.adn.networklayer.com) |
| [{{site.data.keyword.cloud_notm}} Object Storage](/docs/vpc?topic=vpc-connecting-vpc-cos) | `s3.direct.xxx.cloud-object-storage.appdomain.cloud` |
{: caption="Available services" caption-side="bottom"}

The VDC must have an edge (public-private or private-only) to enable access to the service network. NAT and firewall rules for private network connectivity are established as a default during the VDC creation.
{: important}

### Creating a vApp network for {{site.data.keyword.vcf-aas}}
{: #vcd-ops-guide-vapp-network-vmaas}

If not already completed, create a vApp containing at least two VMs before you complete the following procedure. For more information, see [Working with vApps](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-AC48FB5E-4ADC-4835-AACE-B949B297A147.html){: external}.
{: requirement}

1. From the left panel of the tenant portal, click **Data Centers**.
2. From the **Virtual Data Center** details page, click the VDC where you want to create the vApp network.
3. From the **Compute** section of the left panel, click **vApps**.
4. Click the vApp that you want to add a vApp network to.
5. Click the **Networks** tab, and click **NEW** in the **vApp Fencing** section.
6. On the **Add Network to** window, select **OrgVDC Network** and select the network name.
7. Click **Add**.

For more information, see [Working with networks in a vApp](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-FCBC791B-3183-4CD9-A194-856E98CC32D3.html).

### Allocating public IP addresses for NAT rules and for VPNs
{: #vcd-ops-guide-allocating-ips}

Every {{site.data.keyword.vcf-aas}} VDC with a public edge is provided with eight public IP addresses. To enable the eight addresses for use in the edge NAT rules or the Virtual Private Network (VPN) rules, you must first allocate the public addresses.

You must perform these steps as a user who has the **Manage Manual IP Reservation** permission. IBM default roles **Manager**, **Administrator**, **Director Network Admin**, and **Director Security Admin** all have this permission.
{: requirement}

1. From the left panel of the tenant portal, click **Networking**.
2. At the top of the right panel, select **IP Spaces**.
3. Click the IP space name that's associated with the VDC's edge. If you have multiple VDCs with a public edge, you can identify which IP space name is associated to the edge when the first three characters of the IP Space name match the data center that the VDC is created in. For example, **t04** matches tokyo04.

   You can also use the **V00** value in the name, if needed. Under **Configuration** on the **Edge Gateway** details page, click **General**. The **Provider Gateway** name has a **VRF000** value. Use the number in that value, for example **vfr015**. In this example, use the pattern **t04-xxx-V15-xxx** to locate the correct IP Space entry.

4. From the **Allocation** section on the **IP Spaces** details page, select **Floating IPs**.
5. At the top of the table, click **REQUEST**.
6. Each VDC is assigned eight public IP addresses. The request dialog supports a maximum of five IPs per request operation. To ensure that all eight IP addresses are allocated, first request five IPs, then repeat the request for the remaining three IPs.

### Using VPNs to connect VMware workloads to {{site.data.keyword.cloud_notm}}
{: #vcd-ops-guide-vpn-vmaas}

You can use VPNs to connect your VMware workloads through the public network to {{site.data.keyword.vcf-aas}} single-tenant and multitenant instances.

#### Creating a route-based IPsec VPN against the VDC edge gateway over the public internet for {{site.data.keyword.vcf-aas}}
{: #vcd-ops-guide-routebased-ipsec-vpn-vmaas}

The following steps outline a validated process. Many different configurations work and depending on the remote side of the IPsec tunnel, different configurations might be required.

Before you begin, ensure that any edge public egress rules don't use `Any` for the **Internal IP** value. The rules must specify a CIDR of the internal VDC network that supports SNAT egress.

1. From the left panel of the tenant portal, click **Data Centers**.
2. From the **Virtual Data Center** details page, click the VDC where you want to create a route-based IPsec VPN.
3. From the **Networking** section in the left panel, click **Edges**.
4. From the **Services** section in the left panel, click **IPSec VPN**.
5. Click **NEW** and complete the following fields for the IPsec VPN tunnel.
   1. For **General Settings**, complete the following selections and click **NEXT**.
      * For **Name** and **Description**, provide details that help to describe the VPN.
      * For **Type**, select **Route Based**.
      * For **Security Profile**, use the default.
      * For **Status**, toggle to enable.
      * For **Logging**, toggle to disable.
   2. For **Peer Authentication Mode**, complete the following selections and click **NEXT**.
      * For **Authentication Mode**, select **Pre-Shared Key**. You must also use this value on the other side of the VPN tunnel.
      * For **Pre-Shared Key**, enter a secure value that is also used on the other side of the VPN tunnel.
   3. For **Endpoint Configuration**, complete the following selections and click **NEXT**.
      * For **Local Endpoint**, enter an available and unused public IP address. The public IP address must also be allocated in IP Spaces Floating IPs.
      * For **Remote Endpoint**, enter a public IP address from the remote side of the VPN. The address on the remote side of the VPN is called the **Local IP Address**. Leave the **Remote ID** field empty.
      * For **Virtual Tunnel Interfaces (VTI) Tunnel Interface**, set the value to a `/30` or `/31` network in the link-local ranges (169.254.0.0/16). Don't reuse the same tunnel interfaces. Consider the following examples.

      | Local interface   | Remote interface   |
      |:----------------  |:------------------ |
      | 169.254.101.1/30  | 169.254.101.2/30   | 
      | 169.254.110.5/30  | 169.254.110.6/30   | 
      | 169.254.120.9/30  | 169.254.120.10/30  |
      | 169.254.139.13/30 | 169.254.130.14/30  |
      {: caption="Tunnel interface examples" caption-side="bottom"}

   4. Review the settings for accuracy and click **FINISH**.
6. From the **Routing** section in the left panel, click **Static Routes**.
7. Click **NEW** and complete the following fields for the new static route.
   1. For the **General** tab, complete the following selections.
      * For **Name** and **Description**, provide details that help to describe the static route.
      * For **Network**, enter the remote network that the VPN is connecting with. For example, `192.168.47.0/24`.
      * Ensure that the **Route Advertised** field is toggled off.
   2. For the **Next Hops** tab, complete the following selections. 
      * For **IP Address**, enter the tunnel IP address of the remote tunnel. For example, `169.254.101.1`.
      * For **Admin Distance**, enter *1*.
      * For **Scope**, leave the field empty.
   3. Click **SAVE**.

#### Creating a policy-based IPsec VPN against the VDC edge gateway over the public internet for {{site.data.keyword.vcf-aas}}
{: #vcd-ops-guide-policybased-ipsec-vpn-vmaas}

The following steps outline a validated process. Many different configurations work and depending on the remote side of the IPsec tunnel, different configurations might be required.

Before you begin, ensure that any edge public egress rules don't use `Any` for the **Internal IP** value. The rules must specify a CIDR of the internal VDC network that supports SNAT egress.

1. From the left panel of the tenant portal, click **Data Centers**.
2. From the **Virtual Data Center** details page, click the VDC where you want to create a policy-based IPsec VPN.
3. From the **Networking** section in the left panel, click **Edges**.
4. From the **Services** section in the left panel, click **IPSec VPN**.
5. Click **NEW** and complete the following fields for the IPsec VPN tunnel.
   1. For **General Settings**, complete the following selections and click **NEXT**.
      * For **Name** and **Description**, provide details that help to describe the VPN.
      * For **Type**, select **Policy Based**.
      * For **Security Profile**, use the default.
      * For **Status**, toggle to enable.
      * For **Logging**, toggle to disable.
   2. For **Peer Authentication Mode**, complete the following selections and click **NEXT**.
      * For **Authentication Mode**, select **Pre-Shared Key**. You must also use this value on the other side of the VPN tunnel.
      * For **Pre-Shared Key**, enter a secure value that is also used on the other side of the VPN tunnel.
   3. For **Endpoint Configuration**, complete the following selections and click **NEXT**.
      * For **Local Endpoint IP Address**, enter an available and unused public IP address. The public IP address must also be allocated in IP Spaces Floating IPs.
      * For **Local Endpoint Networks**, enter the VDC network CIDR of the local VDC to share over the VPN. For example, `192.168.19.0/24`.    
      * For **Remote Endpoint IP Address**, enter a public IP address from the remote side of the VPN. The address on the remote side of the VPN is called the **Local IP Address**.
      * For **Remote Endpoint Networks**, enter the VDC network CIDR of the remote VDC to share over the VPN. For example, `192.168.47.0/24`.
      * For **Remote ID**, leave the field empty.
   4. Review the settings for accuracy and click **FINISH**.  
  
#### Creating an L2 VPN against the VDC edge gateway over the public internet for {{site.data.keyword.vcf-aas}}
{: #vcd-ops-guide-l2vpn-vmaas}

The following steps outline a validated process. Many different configurations work and depending on the remote side of the L2 VPN, different configurations might be required.

Before you begin, ensure that any edge public egress rules don't use `Any` for the **Internal IP** value. The rules must specify a CIDR of the internal VDC network that supports SNAT egress.

##### Procedure to configure the L2 VPN server
{: #vcd-ops-guide-l2vpn-vmaas-config-server}

1. From the left panel of the tenant portal, click **Data Centers**.
2. From the **Virtual Data Center** details page, click the VDC where you want to create a L2 VPN.
3. In the left panel under **Networking**, click **Edges**.
4. From the **Services** section in the left panel, click **L2 VPN**.
5. Click **NEW** and complete the following fields for the L2 VPN tunnel.
   1. For **Choose Session Mode**, set the session mode to **Server** for the L2 VPN. You set the other side to **Client** in the procedure to configure the L2 VPN client.
   2. For **General Settings**, complete the following selections and click **NEXT**.
      * For **Name** and **Description**, provide details that help to describe the VPN.
      * For **Pre-Shared Key**, enter a secure value.
      * For **State**, toggle to enable.
   3. For **Endpoint Setup**, complete the following selections.
      * For **Local Endpoint**, enter a free and unused public IP address. The public IP address must be allocated in IP Spaces Floating IPs.
      * For **Tunnel Interface CIDR**, set the value to a `/30` or `/31` network in the link-local ranges (169.254.0.0/16). Don't reuse the same tunnel interfaces. Consider the following examples:
        * 169.254.101.1/30
        * 169.254.110.5/30
        * 169.254.120.9/30
        * 169.254.139.13/30
      * For **Remote IP**, enter a public IP address from the remote side of the VPN. The address on the remote side of the VPN is called the **Local IP Address**.
      * For **Initiation Mode** select one of the three options (Initiator, Respond Only or On Demand) and click **NEXT**.
   4. For **Org VDC Networks**, select the VDC network to participate in the L2 VPN and click **NEXT**.
      
      Both ends of the L2 VPN must use the same network IP ranges with unique IP assignments to servers and VMs across both ends of the VPN. For example, the L2 VPN connects one end of the tunnel with a network that uses `192.168.50.10-192.168.50.100` to the other end with network that uses `192.168.50.101-192.168.50.190`.
      {: tip}

   5. Review the settings for accuracy and click **FINISH**.

##### Procedure to configure the L2 VPN client
{: #vcd-ops-guide-l2vpn-vmaas-config-client}

1. From the left panel of the tenant portal, click **Data Centers**.
2. From the **Virtual Data Center** details page, click the VDC where you want to create the L2 VPN.
3. In the **Networking** section in the left panel, click **Edges**.
4. From the **Services** section in the left panel, click **L2 VPN**.
5. Click **NEW** and complete the following fields for the L2 VPN tunnel.
   1. For **Choose Session Mode**, set the session mode to **Client** for the L2 VPN. The other side is **Server**.
   2. For **General Settings**, complete the following selections and click **NEXT**.
      * For **Name** and **Description**, provide details that help to describe the VPN.
      * For **Peer Code**, use the value from the server side of the L2 VPN. If the server side is a Director VDC, complete the following steps from the VDC that is the server-side of the L2 VPN.
        1. From the left panel under **Networking**, click **Edges**.
        2. From the **Services** section in the left panel, select **L2 VPN** and select the L2 VPN Server from the list.
        3. Above the table, click **Copy peer code**.
        4. Paste the peer code value in the client L2 VPN **Peer Code* input** field. 
        5. For **State**, toggle to enable.
   3. For **Endpoint Setup**, complete the following selections and click **NEXT**.
      * For **Local Endpoint**, enter an available and unused public IP address. The IP address is the same address that is used in the L2 VPN server config as the **Remote IP**. The IP address must also be allocated in IP Spaces Floating IPs.
      * For **Remote IP**, enter a public IP address from the remote side of the L2 VPN. The address on the Server side of the VPN is called the **Local IP Address**.
   4. For **Org VDC Networks**, complete the following selections and click **NEXT**.
      * Select the VDC network to extend over the L2 VPN.

      Both ends of the L2 VPN must use the same network IP ranges with unique IP assignments to servers and VMs across both ends of the VPN. For example, the L2 VPN connects one end of the tunnel with a network that uses `192.168.50.10-192.168.50.100` to the other end with network that uses `192.168.50.101-192.168.50.190`.
      {: tip}

      * For **Tunnel ID**, use incrementing numbers for each L2 VPN tunnel. For the first tunnel, use `1`. For the second tunnel, use `2` and so on.
   5. Review the settings for accuracy and click **FINISH**.

## Accessing Operations Manager
{: #vcd-ops-guide-enable-chargeback}

The Operations Manager service is enabled by default. From the Cloud Director tenant portal, click **More > Operations Manager** to access the Operations Manager web UI.

For more information about using Operations Manager, see [Using VMware Chargeback as a Tenant](https://docs.vmware.com/en/Management-Packs-for-vRealize-Operations/8.10/vmware-chargeback-for-vcd-for-a-tenant/GUID-4D7030B6-AF73-464B-8FE8-75B879EE76B8.html).{: external}

Use Operations Manager to view VDC, vApp, and VM level metrics and to export metric data. You can use this data to isolate resource usage and to help understand billing charges.
{: note}

## Related links
{: #vcd-ops-guide-related}

* [VMware Cloud Director Tenant Portal Guide](https://docs.vmware.com/en/VMware-Cloud-Director/10.5/VMware-Cloud-Director-Tenant-Guide/GUID-74C9E10D-9197-43B0-B469-126FFBCB5121.html){: external}
