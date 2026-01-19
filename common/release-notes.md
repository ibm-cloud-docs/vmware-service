---

copyright:
  years: 2022, 2026

lastupdated: "2026-01-19"

keywords: release notes, what's new in VMware Cloud Foundation as a Service, what is new, new features, vmware release notes, VMware Cloud Foundation as a Service, VCF as a Service

subcollection: vmware-service

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.vcf-aas}}
{: #vmware-service-relnotes}

{{site.data.content.vms-deprecated-note}}

Use these release notes to learn about the most recent updates to {{site.data.keyword.vmware-service_notm}}, including new features, component updates, usability enhancements, and bug fixes.
{: shortdesc}

## 2026
{: #vmware-service-year-2026}



### 19 January 2026
{: #vmware-service-jan1926}
{: release-note}

Updated pricing for {{site.data.keyword.vcf-aas-full}}
:   As of 1 January 2026, the prices are increased for Veeam® software. The regional pricing is also increased for {{site.data.keyword.vcf-aas}}.

   * Veeam software price is increased from $13 per VM per month to $15.60 per VM per month.
   * The pricing is also increased for the following regions:
      * Toronto - from 3% to 6%
      * London - from 7% to 13%
      * Frankfurt - from 10% to 16%
      * Madrid - from 10% to 16%
      * Tokyo - from 13% to 22%
      * Sydney - from 20% to 22%
      * Sao Paulo - from 20% to 38%

   You can also review the updated pricing details on the Summary section of the related ordering page. For more information, see the [{{site.data.keyword.cloud}} announcement](https://cloud.ibm.com/notifications?selected=1767799886080){: external}.

## 2025
{: #vmware-service-year-2025}

### 9 December 2025
{: #vmware-service-dec0925}
{: release-note}

Software currency updates
:   This release provides the following infrastructure upgrades:

   * VMware vCenter Server® Appliance 8.0 Update 3g
   * VMware vCloud Usage Meter 9.0.1

### 27 October 2025
{: #vmware-service-oct2725}
{: release-note}

End of Marketing for VMware on {{site.data.keyword.cloud_notm}}
:   As of 31 October 2025, new deployments of VMware Solutions offerings are no longer available for new customers. Existing customers can still use and expand their active VMware workloads on {{site.data.keyword.cloud_notm}}. For more information, see [End of Marketing for VMware on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vms).

### 22 September 2025
{: #vmware-service-sep2225}
{: release-note}

Software currency update
:   This release provides an infrastructure upgrade for NSX-T™ 4.2.3.

Bring Your Own Key for dedicated workloads
:   You can open an {{site.data.keyword.IBM}} Support ticket to Bring Your Own Key (BYOK) for dedicated workload virtual machine (VM) encryption. An {{site.data.keyword.keymanagementservicefull_notm}} instance is required for customer-managed keys. For more information, see [Bring Your Own Key for dedicated workloads](/docs/vmware-service?topic=vmware-service-byok-dedicated).

Migration and disaster recovery for on-premises VMware Cloud Director instances
:   You can open an IBM Support ticket to create a VCDA connection from your on-premises VMware Cloud Director™ instance to {{site.data.keyword.vcf-aas-full}}. For more information, see [Connecting VMware Cloud Director instances to VCF as a Service](/docs/vmware-service?topic=vmware-service-vcda-vdc-connect).

### 8 August 2025
{: #vmware-service-aug825}
{: release-note}

New cost-effective Veeam Backup options
:   You can open an IBM Support ticket to request a dedicated IBM Cloud Object Storage only Scale-out Backup Repository (SOBR) for your Veeam backups. For more information, see [Using cost-effective Veeam Backup options with a dedicated Scale-out Backup Repository](/docs/vmware-service?topic=vmware-service-veeam-adding-sobr).

Software currency updates
:   This release provides the following infrastructure upgrades:

   * NSX-T 4.2.2.1
   * VMware Cloud Director 10.6.1.1
   * VMware ESXi™ 8.0 Update 3f
   * Veeam Backup 12.3.2

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-8-august-2025).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

New documentation
:   A new topic, [{{site.data.keyword.vcf-aas}} pricing](/docs/vmware-service?topic=vmware-service-vmaas_pricing), is now available to help you understand pricing and billing considerations for {{site.data.keyword.vcf-aas}}.

### 26 June 2025
{: #vmware-service-june2625}
{: release-note}

IBM Cloud data center support for Sao Paulo
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Sao Paulo region to host your single-tenant and multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 23 May 2025
{: #vmware-service-may2325}
{: release-note}

Public IP enhancements
:   You can open an IBM Support ticket to request additional public IP addresses. For more information, see [Requesting additional public IP addresses](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-additional-ips).

Software currency update
:   This release provides the infrastructure upgrades for Veeam Backup 12.3.1.

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-23-may-2025).

### 28 April 2025
{: #vmware-service-apr2825}
{: release-note}

Multitenant compute regional high availability resource pool support in Washington DC
:   A new multizone resource pool in the **Washington DC** region is now available for workloads that require 99.99% infrastructure availability. The Washington DC resource pool offers cross-data center high availability for both networking and compute resources. Additional compute regional high availability resource pools will be made available in other locations soon.

### 7 April 2025
{: #vmware-service-apr725}
{: release-note}

vSAN stretched workload support
:  You can now create stretched vSAN™ high availability resource pools for existing single-tenant Cloud Director sites. The resource pool stretches across two data centers in a multizone region to increase availability and to protect critical workloads from unexpected downtime.

   With vSAN stretched support, you can order a single-tenant or multitenant virtual data center (VDC) on a stretched resource pool.

   Stretched resource pools are available only on some multitenant Cloud Director sites. Additional stretched resource pools will be made available over time.
   {: note}

Network regional high availability
:  To ensure high performance and effective load distribution, you can now order a regional high availability edge when you create a new single-tenant or multitenant VDC. Either deploy the regional high availability edge on a stretched resource pool or consolidate your network across two resource pools in a multizone region. For additional information, see [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding).

Immutable IBM Cloud Object Storage availability
:   Immutable {{site.data.keyword.cloud_notm}} Object Storage provides an extra layer of security, by default, for shared SOBRs or when you order a dedicated SOBR through the Veeam Backup service for your single-tenant and multitenant instances. For more information, see [Managing Veeam for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-tenant-veeam#tenant-veeam-storage).

Software currency update
:   This release provides an infrastructure upgrade for VMware NSX-T 4.2.1.2.

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-7-april-2025).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.
   * The **Profile CPU type** field for Cascade Lake and Sapphire Rapids profiles is added to the cluster configuration for Cloud Director site and cluster orders.
   * The option to swap the primary and secondary network locations for a highly available network edge is available on the VDC summary page.

### 24 March 2025
{: #vmware-service-mar2425}
{: release-note}

IBM Cloud data center support for Madrid multitenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Madrid region to host your multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 4 March 2025
{: #vmware-service-mar425}
{: release-note}

IBM Cloud data center support for Madrid single-tenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Madrid region to host your single-tenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 14 February 2025
{: #vmware-service-feb1425}
{: release-note}

Intel Sapphire Rapids server availability
:   The following Intel Sapphire Rapids bare metal servers are now available for NFS and vSAN™ ESA host profiles, available only on vSphere 8. For more information, see the *Host profile* section in [Planning for deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-cluster-host).

   * Dual Intel® 6416H Xeon® Platinum
   * Dual Intel 8474C Xeon Platinum

Software currency update
:   This release provides the infrastructure upgrades for Veeam Backup 12.3.

Enhanced log access
:   Firewall logs are now available on the VMware Cloud Director™ tenant portal. For more information, see [Viewing firewall logs for your edge gateway](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-firewall-logs).

   Additionally, the *Organization vDC Gateway: Configure System Logging* right is now available with this release.

    If you use pre-configured Open ID Connect roles or any role other than the Organization Administrator role, you must manually update the rights to your roles. For more information about the recommended OIDC roles to use with the new right, see [Recently introduced rights](/docs/vmware-service?topic=vmware-service-vmaas-iam_vcd#vmaas-iam_vcd-custom-reqs).
    {: note}

VMware Cloud Director Snapshots availability
:   You no longer need to open an IBM Support ticket to enable VMware Cloud Director Snapshots. By default, the snapshot limit is now set to 31.

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-14-february-2025).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.
   * The **{{site.data.keyword.vmware-service_short}}** resource page provides a new resource list view to better organize the Cloud Director site and VDC relationship and details. You can switch to the original resource list view.
   * The {{site.data.keyword.vmware-service_short}} site details page for single-tenant instances provides the following improvements.
      * The **Networking** tab now provides edge and VDC details.
      * The **Resource pool** tab replaces the **Infrastructure** tab. The **Resource pool** tab provides location, compute, storage, cluster, and host details.
      * A new **Virtual data centers** tab provides a summary of VDCs deployed on the Cloud Director site.

## 2024
{: #vmware-service-year-2024}

### 13 December 2024
{: #vmware-service-dec24}
{: release-note}

Intel Sapphire Rapids server availability
:   Dual Intel 8474C Xeon® bare metal servers are now available for vSAN ESA host profiles, available only on vSphere 8. For more information, see [Planning for deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-cluster-host).

Software currency update
:   This release provides an infrastructure upgrade for Veeam Backup 12.2 HF 7.7.

VMware Cloud Director Snapshots
:   You can now open an IBM Support ticket to enable VMware Cloud Director Snapshots to take multiple images of your virtual machines. Include the following details in the support ticket:
   * The snapshot count. You can request up to 31 images per virtual machine.
   * The URL to the {{site.data.keyword.vcf-aas}} Cloud Director site.
   * Your VMware Cloud Director Organization ID.

Promotion code availability for new {{site.data.keyword.vcf-aas}} pay-as-you-go customers
:    A new $1,000 limited-time credit promotion code, **VCFAAS1000**, is available for new {{site.data.keyword.vcf-aas}} pay-as-you-go customers. Apply the promotion code during the provision process for any new {{site.data.keyword.vcf-aas}} offering.

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.
   * The **VMware Cloud Foundation as a Service** resource page provides guidance about the next steps to use your VCF as a Service instance.
   * The **Summary** tab of the Cloud Director site details page is better organized for you to view important information at a glance.

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-13-december-2024).

### 10 December 2024
{: #vmware-service-dec1024}
{: release-note}

IBM Cloud data center support for Sydney multitenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Sydney region to host your multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 9 December 2024
{: #vmware-service-dec0924}
{: release-note}

IBM Cloud data center support for Sydney single-tenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Sydney region to host your single-tenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 25 November 2024
{: #vmware-service-nov2524}
{: release-note}

IBM Cloud data center support for London multitenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the London region to host your multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 11 November 2024
{: #vmware-service-nov1124}
{: release-note}

Supported VPNs for {{site.data.keyword.vcf-aas}}
:   You can now use route-based IPsec, policy-based IPsec, and L2 VPNs to connect your VMware workloads through the public network to {{site.data.keyword.vcf-aas}} single-tenant and multitenant instances. For more information, see [Operating VMware Cloud Director](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-routebased-ipsec-vpn-vmaas).

Software currency update
:   This release provides an infrastructure upgrade for VMware vCenter Server Appliance 8.0 Update 3d.

### 25 October 2024
{: #vmware-service-oct2524}
{: release-note}

VMware Cloud Director IP Spaces availability
:   Beginning with VMware Cloud Director 10.6, {{site.data.keyword.vcf-aas}} is moving to an updated edge architecture along with the use of IP Spaces. With this update, the networking views on the VMware console are updated. Most noticeably, the BGP settings are now located in the **Provider Gateways** view instead of the **Edge Gateways** view and include more views such as BGP summary and the option to download the routing table.

   By default, each VDC with the public and private network edge connection is now provisioned with eight public IP addresses and one private IP address that is used for accessing the {{site.data.keyword.cloud_notm}} private network. All public OS templates, by default, now have routability to the {{site.data.keyword.cloud_notm}} private network, including licensed OS activation, OS updates, NTP, DNS, and Cloud Object Storage.

   IP addresses are managed differently with this update and introduce changes to creating NAT and firewall rules. For more information, see [Allocating public IP addresses for NAT rules and for VPNs](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-allocating-ips).

 New rights availability
 :   Additional rights are available with this release. If you use pre-configured Open ID Connect roles or any role other than the Organization Administrator role, you must manually update the rights to your roles. For more information, see [Recently introduced rights](/docs/vmware-service?topic=vmware-service-vmaas-iam_vcd#vmaas-iam_vcd-custom-reqs).

Software currency updates
:   This release provides the following infrastructure upgrades:

   * VMware Cloud Director 10.6.0.1
   * VMware vCenter Server Appliance 8.0 Update 3b
   * VMware NSX-T 4.2.0.2
   * Veeam Backup 12.2
   * VMware Cloud Director Availability 4.7.3

### 15 October 2024
{: #vmware-service-oct1524}
{: release-note}

IBM Cloud data center support for London single-tenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the London region to host your single-tenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 24 September 2024
{: #vmware-service-sep2424}
{: release-note}

IBM Cloud data center support for Toronto multitenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Toronto region to host your multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 13 September 2024
{: #vmware-service-sep1324}
{: release-note}

Disaster recovery with VMware Cloud Director Availability
:   You can now use VMware Cloud Director Availability (VCDA) to configure a disaster recovery plan for your primary workload environment. For more information, see [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda-dr).

{{site.data.keyword.tg_full_notm}} connection enhancements
:   You can now connect to a {{site.data.keyword.tg_short}} instance in a region different from the Cloud Director site. For more information, see [Using Transit Gateway to interconnect VCF as a Service with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections).

Software currency update: VMware Cloud Director Availability 4.7.2
:   This release provides infrastructure upgrades to VMware Cloud Director Availability 4.7.2.

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-13-september-2024).

New documentation
:   A new solution tutorial, [Configuring disaster recovery with VMware Cloud Director Availability](/docs/vmware-service?topic=vmware-service-vcda-creating-dr-config), is now available.

### 23 August 2024
{: #vmware-service-aug2324}
{: release-note}

IBM Cloud data center support for Toronto single-tenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Toronto region to host your single-tenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 16 August 2024
{: #vmware-service-aug1624}
{: release-note}

Software currency update: VMware vCenter Server Appliance 8.0 Update 2d
:   This release provides infrastructure upgrades to VMware vCenter Server Appliance 8.0 Update 2d.

Terraform
:   {{site.data.keyword.vcf-aas}} provides Terraform in addition to APIs for creating, updating, and deleting {{site.data.keyword.vcf-aas}} VDCs. For more information, see the [Terraform registry](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/vmaas_vdc). {: external}

### 1 August 2024
{: #vmware-service-aug0124}
{: release-note}

IBM Cloud data center support for Tokyo multitenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Tokyo region to host your multitenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 15 July 2024
{: #vmware-service-jul2024}
{: release-note}

IBM Cloud data center support for Tokyo single-tenant
:   {{site.data.keyword.vcf-aas}} expands global presence and now supports the Tokyo region to host your single-tenant VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 14 June 2024
{: #vmware-service-jun2024}
{: release-note}

Private network connection availability for virtual data center orders
:   You can now select either a public and private network connection or a private-only network connection when you create your VDC with a network edge. For more information, see [Network settings](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-network).

Scale-out Backup Repository for Veeam Backup
:   The Veeam Backup service now provides the option to order a dedicated SOBR for your single-tenant and multitenant instances. For more information, see [Ordering a dedicated Scale-out Backup Repository](/docs/vmware-service?topic=vmware-service-veeam-adding-sobr).

VMware Operations Manager availability
:   You can now access the Operations Manager service through the VMware Cloud Director tenant portal. Use Operations Manager to view your virtual machine metrics for new and existing organizations. For more information, see [Accessing Operations Manager](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-services-chargeback).

Software currency
:   This release provides the following infrastructure upgrades:

   * VMware ESXi 7.0 Update 3q
   * VMware vCenter Server Appliance 8.0 Update 2c
   * VMware NSX-T 4.1.2.4
   * Veeam Backup 12.1.2

REST API updates
:   The [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service) is updated with additional features. For more information, see the [{{site.data.keyword.vcf-aas}} API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-14-june-2024).

### 1 May 2024
{: #vmware-service-may2024}
{: release-note}

Updated offerings for VMware Solutions
:   Existing {{site.data.keyword.vmwaresolutions_short}} offerings are no longer available as separate components and are replaced by VMware Cloud Foundation. The following offering name changes are available across the portfolio, including the documentation and REST API.

   * VMware as a Service is now called **{{site.data.keyword.vmware-service_short}}** or **{{site.data.keyword.vcf-aas}}**.
   * VMware vCenter Server, VMware vSphere, Cyber Recovery, and Regulated Workloads are merged into **{{site.data.keyword.vcf-classic}}** or **{{site.data.keyword.vcf-classic-short}}**.
   * VMware Cloud Foundation is now called **{{site.data.keyword.vcf-vpc}}** or **{{site.data.keyword.vcf-vpc-short}}**.

For more information, see [Packaging and pricing for VMware by Broadcom](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_packaging-pricing).

Some documentation, including, but not limited to, tutorials, solutions architectures, solution guides, videos, and diagrams might still be using the old offering names. This information will be gradually updated to the new offering names in future releases.
{: note}

Software currency
:   This release provides the following infrastructure upgrades:

   * VMware Cloud Director 10.5.1.1
   * VMware vCenter Server Appliance 8.0 Update 2b (00200)
   * VMware Cloud Director Availability 4.7.1

New host profiles for NFS and vSAN clusters
:   Additional bare metal server configurations are available for new and existing {{site.data.keyword.vcf-aas}} Cloud Director site orders. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-cluster-host).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * You can now review specifications and pricing on the order page to help you choose the {{site.data.keyword.vcf-aas}} instance type and features that you want to order.
   * You can now access the VMware Cloud Director Availability (VCDA) console from the **Add-on services** tab on the virtual data center details page.

### 1 April 2024
{: #vmware-service-apr2024}
{: release-note}

Updated packaging and pricing for VMware Solutions offerings
:   {{site.data.keyword.cloud_notm}} is changing its {{site.data.keyword.vmwaresolutions_short}} portfolio and pricing, in response to the changes to the packaging and pricing of the VMware® portfolio, announced by Broadcom. These changes will be effective on 1 May 2024. For more information, see [Packaging and pricing for VMware by Broadcom](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_packaging-pricing).

Updated pricing structure for RHEL for VMware as a Service
:   The Red Hat Enterprise Linux (RHEL) pricing is updated from the existing 2-tier pricing structure (Small and Large) to a 3-tier pricing structure (Small, Medium, and Large). For more information, see [April 2024 price changes](/docs/overview?topic=overview-price-adjustments).

### 15 March 2024
{: #vmware-service-mar2024}
{: release-note}

Software currency
:   This release provides the following infrastructure upgrades:

   * VMware ESXi 7.0 Update 3p (23307199)
   * VMware vCenter Server Appliance 7.0 Update 3p (01800)
   * Veeam Backup 12.1.1

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * A **Help me choose** option is now available on the order page to guide you through the process of ordering a VMware as a Service instance.
   * The contents of the **Summary** tabs for both single-tenant and multitenant VDCs are better structured and organized for a more streamlined user experience.

REST API updates
:   The [VMware as a Service API](/apidocs/vmware-service) is updated to support enabling or disabling Veeam and VMware Cloud Director Availability (VCDA) on a VMware Cloud Director site. For more information, see the [VMware as a Service API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-15-march-2024).

New and updated documentation
:   The [Architecture patterns for integrating IBM Cloud Security and Compliance Center Workload Protection with VMware as a Service](/docs/vmware-service?topic=vmware-service-arch-pattern-vmwaas-sccwpp) technical document is now available.

### 9 February 2024
{: #vmware-service-feb2024}
{: release-note}

{{site.data.keyword.cloud_notm}} private-only networking
:   VMware as a Service now offers private-only networks for management connectivity for accessing VMware Cloud Director and workload connectivity for accessing your VMware as a Service workloads. For private-only workload connections, connect VDCs to {{site.data.keyword.tg_full_notm}} to connect to workloads outside of the private network. For more information, see [Network settings](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-network).

{{site.data.keyword.tg_full_notm}}
:   You can now use {{site.data.keyword.tg_short}} to securely interconnect VMware as a Service multitenant and single-tenant VDCs to a transit gateway to enable network connectivity into your {{site.data.keyword.cloud_notm}} Classic and Virtual Private Cloud (VPC) IaaS infrastructures, and your on-premises locations by using Direct Link connections. For more information, see [Using Transit Gateway to interconnect VMware as a Service with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

REST API updates
:   The [VMware as a Service API](/apidocs/vmware-service) is updated to provide support for VMware Cloud Director Availability (VCDA), OpenID Connect (OIDC) configuration, and {{site.data.keyword.tg_full_notm}}. For more information, see the [VMware as a Service API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-9-february-2024).

### 12 January 2024
{: #vmware-service-jan2024}
{: release-note}

Base charge reduction for on-demand multitenant instances
:   The base charge for VMware as a Service on-demand multitenant instances is adjusted to $0.00 per month. The six public IP addresses are instead included in the efficiency edge charge.

User interface updates and enhancements
:   The user interface is updated with various message and tooltips that include the following enhancements.

   * The term **provider virtual data center** is updated to **resource pool** throughout the UI, user documentation, and REST APIs.
   * The **Infrastructure** tab on the Cloud Director site details page is updated to **Resource pool**.

New documentation
:   A new solution tutorial, [Creating a VPN between the virtual data center edge gateway and the on-premises VPN gateway](/docs/vmware-service?topic=vmware-service-vmwaas-ipsec-tunnel), is now available. This tutorial provides the steps to connect a VMware as a Service instance with Juniper® vSRX. 

## 2023
{: #vmware-service-year-2023}

### 15 December 2023
{: #vmware-service-dec2023}
{: release-note}

Cloud-to-cloud migration to VMware as a Service
:   You can now use cloud-to-cloud connections to migrate {{site.data.keyword.vmwaresolutions_short}} Shared instances to VMware as a Service. You can also use cloud-to-cloud connections to migrate workloads from single-tenant and multitenant VMware as a Service instances to another VMware as a Service instance. For more information, see [Creating and deleting VMware as a Service pairings](/docs/vmware-service?topic=vmware-service-vcda-creating-deleting-vmaas-pairing).

vSAN host profile updates
:   The Dual Intel 8260 Xeon host profile (4 Sockets - 96 Cores, 1536 GB RAM) with 61 TB of VMware vSAN usable capacity is now available for Cloud Director sites.

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

New documentation
:   A number of solution tutorials are now available under the **Tutorials** section of the VMware as a Service documentation. These tutorials provide step-by-step instructions about using VMware as a Service to implement common patterns based on best practices.

### 17 November 2023
{: #vmware-service-nov2023}
{: release-note}

Migrating virtual machines to VMware as a Service
:   The VMware Cloud Director Availability (VCDA) service is now available as a cost-effective solution to easily migrate your VMware vCenter Server or on-premises workloads to the VMware as a Service single-tenant consumption model. Use enterprise-level VCDA to migrate virtual machines over a secure public internet connection at no cost. For more information, see [VMware Cloud Director Availability for VMware as a Service overview](/docs/vmware-service?topic=vmware-service-tenant-vcda).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

Documentation updates and enhancements
:   The table of contents is updated for a more streamlined user experience.

### 20 October 2023
{: #vmware-service-oct2023}
{: release-note}

VMware as a Service Multitenant
:   This release announces the VMware as a Service Multitenant consumption model. VMware as a Service Multitenant provides a flexible, pay-per-use option to deploy VDCs on an IBM-managed Cloud Director site. You can get started quickly by selecting from on-demand or reserved pricing plans, and then add CPU, RAM, and storage as needed. Additionally, the Veeam Backup service is available for you to install to securely protect and provide a recovery option for your workloads. For more information, see [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).

REST API updates
:   The [VMware as a Service API](/apidocs/vmware-service) is updated to provide support for VMware as a Service Multitenant. For more information, see [VMware as a Service API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-20-october-2023).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

### 22 September 2023
{: #vmware-service-sep2223}
{: release-note}

IBM Cloud data center availability
:   VMware as a Service expands global presence and now supports the **Washington DC** region to host your provider virtual data center. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

SAP-certified provider virtual data centers
:   VMware as a Service now supports SAP® workloads that use the new SAP bare metal server profiles. You can reliably run your mission-critical SAP workloads and scenarios on a scalable, compliant, and enterprise-proven VMware® by Broadcom platform.
 For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

vSAN host profile updates
:   The Dual Intel 8260 Xeon host profile (2 Sockets - 48 Cores, 768 GB RAM) with 46 TB of vSAN usable capacity is now available for Cloud Director sites.

### 25 August 2023
{: #vmware-service-aug2523}
{: release-note}

User interface updates and enhancements and production refresh
:   The user interface is updated with various message and tooltip enhancements. Performance and security currency improvements are also included in this refresh.

### 18 August 2023
{: #vmware-service-aug1823}
{: release-note}

Production refresh
:   Production refresh to deliver defect resolutions, performance improvements, and maintain security currency.

### 7 July 2023
{: #vmware-service-jul0723}
{: release-note}

Veeam Backup availability
:   The Veeam Backup service is now available by default for deployment with new and existing VMware as a Service instances. Service charges are incurred only if you choose to include the service in your order. For more information, see [Managing Veeam for VMware as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * The ordering flow for both VMware as a Service single-tenant Cloud Director sites and associated VDCs are now combined into a single ordering page.
   * The VMware as a Service **Resources** page now provides two tabbed views. In the first tab, all VDCs in the account are displayed. In the second tab, all authorized Cloud Director sites are displayed with the associated VDCs.
   * You can now access the VMware console from the virtual data center and Cloud Director site summary pages.
   * The **Add-on services** tab is available on instance details pages to easily manage the Veeam Backup service.

### 2 June 2023
{: #vmware-service-jun0223}
{: release-note}

IBM Cloud data center availability
:   (Updated on 30 June 2023) The **Frankfurt** region is now available to host your provider virtual data center. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

Accessing VMware as a Service REST APIs
:   You can now access VMware as a Service APIs through the {{site.data.keyword.cloud_notm}} Virtual Private Cloud. For more information, see [Using a virtual private endpoint](/docs/vmware-service?topic=vmware-service-virtual-private-endpoints).

Fast provisioning for virtual machines
:   Fast provisioning for virtual machines is now available for your VDCs. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

VMware currency
:   This release provides infrastructure upgrades to VMware NSX-T 4.1 and VMware ESXi 7.0U3L.

User interface updates and enhancements
:   You can check the prices for VMware as a Service without having to sign in to {{site.data.keyword.cloud_notm}}. However, you might have limited access to some sections of the ordering pages. To place an order, or for a complete access to the ordering pages, you must log in to {{site.data.keyword.cloud_notm}}.

### 5 May 2023
{: #vmware-service-may0523}
{: release-note}

vSAN storage availability
:   You can now select vSAN storage with optional NFS storage for your instance order in locations with 25 GbE availability. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).

REST APIs
:   REST APIs are now available for all VMware as a Service capabilities. For more information, see [VMware as a Service API](/apidocs/vmware-service).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

### 7 April 2023
{: #vmware-service-apr0723}
{: release-note}

Production refresh
:   Production refresh to deliver defect resolutions, performance improvements, and maintain security currency.

### 10 March 2023
{: #vmware-service-mar1023}
{: release-note}

Data center support for 25 GbE
:   You can now select a data center with networking speed of either 10 GbE or 25 GbE.

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements. Additionally, **Dark** mode is now enabled.

IBM software currency policy
:   Documentation is now available describing how {{site.data.keyword.IBM_notm}} maintains software currency for VMware and third-party software. For more information, see [Understanding IBM software currency policy](/docs/vmware-service?topic=vmware-service-policies).

### 10 February 2023
{: #vmware-service-feb1023}
{: release-note}

VMware currency
:   Infrastructure upgrade to VMware NSX-T 4.0 and VMware Cloud Director 10.4.1. This release resolves various issues, includes several deprecations, and introduces new features, such as API tokens and edge static routes.

Multiple clusters support
:   The limitation of one cluster per provider virtual data center (PVDC) is removed. For more information, see [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting).

Virtual data centers without edge
:   You can deploy VDCs without a network edge, which can help you save resources and costs by sharing an existing edge across multiple VDCs. This option is suitable for centralized networking administration and control over many VDCs. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

### 18 January 2023
{: #vmware-service-jan1823}
{: release-note}

Multizone support
:   You can now create PVDCs across three data centers in the region. For more information, see [Ordering VMware as a Service instances](/docs/vmware-service?topic=vmware-service-tenant-ordering) and [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

Add PVDC with new cluster
:   Adding multiple PVDCs with new clusters is now supported, with a limitation of one cluster per PVDC. For more information, see [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

IAM enablement
:   VMware Cloud Director SSO is enabled with {{site.data.keyword.cloud_notm}} IAM (Identity and Access Management) for new sites. You can also enable IAM for existing sites. After you integrate your site with IAM, you can use single sign-on to log in to the VMware Cloud Director console from the VMware Solutions console. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmware-service?topic=vmware-service-iam-integration).

## 2022
{: #vmware-service-year-2022}

### 14 November 2022
{: #vmware-service-nov1422}
{: release-note}

VMware as a Service released
:   IBM Cloud for VMware as a Service is released! For more information, see [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).
