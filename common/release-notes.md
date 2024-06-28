---

copyright:
  years: 2022, 2024

lastupdated: "2024-06-28"

keywords: release notes, what's new in VMware Cloud Foundation as a Service, what is new, new features, vmware release notes, VMware Cloud Foundation as a Service, VCF as a Service

subcollection: vmware-service

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.vcf-aas}}
{: #vmware-service-relnotes}

Use these release notes to learn about the most recent updates to {{site.data.keyword.vmware-service_full}}, including new features, component updates, usability enhancements, and bug fixes.
{: shortdesc}

## 2024
{: #vmware-service-year-2024}

### July 2024
{: #vmware-service-jul2024}
{: release-note}

IBM Cloud data center availability
: {{site.data.keyword.vcf-aas-full}} expands global presence and now supports the Tokyo region to host your VMware workloads. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

### 14 June 2024
{: #vmware-service-jun2024}
{: release-note}

Private network connection availability for virtual data center orders
: You can now select either a public and private network connection or a private-only network connection when you create your virtual data center with a network edge. For more information, see [Network settings](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-network).

Scale-out Backup Repository for Veeam Backup and Replication
: The Veeam® Backup and Replication service now provides the option to order a dedicated Scale-out Backup Repository (SOBR) for your single-tenant and multitenant instances. For more information, see [Ordering a dedicated Scale-out Backup Repository](/docs/vmware-service?topic=vmware-service-veeam-adding-sobr).

VMware Operations Manager availability
:   You can now access the Operations Manager service through the VMware Cloud Director™ tenant portal. Use Operations Manager to view your virtual machine metrics for new and existing organizations. For more information, see [Accessing Operations Manager](/docs/vmware-service?topic=vmware-service-vcd-ops-guide#vcd-ops-guide-enable-chargeback).

Software currency
:   This release provides the following infrastructure upgrades.

   * VMware ESXi™ 7.0 Update 3q
   * VMware vCenter Server® Appliance 8.0 Update 2c
   * VMware NSX-T™ 4.1.2.4
   * Veeam Backup and Replication 12.1.2

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
:   This release provides the following infrastructure upgrades.

   * VMware Cloud Director 10.5.1.1
   * VMware vCenter Server Appliance 8.0 Update 2b (00200)
   * VMware Cloud Director Availability 4.7.1

New host profiles for NFS and vSAN clusters
:   Additional bare metal server configurations are available for new and existing {{site.data.keyword.vcf-aas}} Cloud Director site orders. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-host-bms-req).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * You can now review specifications and pricing on the order page to help you choose the {{site.data.keyword.vcf-aas}} instance type and features that you want to order.
   * You can now access the VMware Cloud Director Availability (VCDA) console from the **Add-on services** tab on the virtual data center details page.

### 1 April 2024
{: #vmware-service-apr2024}
{: release-note}

Updated packaging and pricing for VMware Solutions offerings
:   {{site.data.keyword.cloud}} is changing its {{site.data.keyword.vmwaresolutions_short}} portfolio and pricing, in response to the changes to the packaging and pricing of the VMware® portfolio, announced by Broadcom. These changes will be effective on 1 May 2024. For more information, see [Packaging and pricing for VMware by Broadcom](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_packaging-pricing).

Updated pricing structure for RHEL for VMware as a Service
:   The Red Hat Enterprise Linux (RHEL) pricing is updated from the existing 2-tier pricing structure (Small and Large) to a 3-tier pricing structure (Small, Medium, and Large). For more information, see [April 2024 price changes](/docs/overview?topic=overview-price-adjustments).

### 15 March 2024
{: #vmware-service-mar2024}
{: release-note}

Software currency
:   This release provides the following infrastructure upgrades.

   * VMware ESXi 7.0 Update 3p (23307199)
   * VMware vCenter Server® Appliance 7.0 Update 3p (01800)
   * Veeam Backup and Replication 12.1.1

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * A **Help me choose** option is now available on the order page to guide you through the process of ordering a VMware as a Service instance.
   * The contents of the **Summary** tabs for both single-tenant and multitenant virtual data centers are better structured and organized for a more streamlined user experience.

REST API updates
:   The [VMware as a Service API](/apidocs/vmware-service) is updated to support enabling or disabling Veeam and VMware Cloud Director Availability (VCDA) on a VMware Cloud Director™ site. For more information, see the [VMware as a Service API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-15-march-2024).

New and updated documentation
:   The [Architecture patterns for integrating IBM Cloud Security and Compliance Center Workload Protection with VMware as a Service](/docs/vmware-service?topic=vmware-service-arch-pattern-vmwaas-sccwpp) technical document is now available.

### 9 February 2024
{: #vmware-service-feb2024}
{: release-note}

{{site.data.keyword.cloud_notm}} private-only networking
:   VMware as a Service now offers private-only networks for management connectivity for accessing VMware Cloud Director and workload connectivity for accessing your VMware as a Service workloads. For private-only workload connections, connect virtual data centers to {{site.data.keyword.tg_full_notm}} to connect to workloads outside of the private network. For more information, see [Network settings](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-network).

{{site.data.keyword.tg_full_notm}}
:   You can now use {{site.data.keyword.tg_short}} to securely interconnect VMware as a Service multitenant and single-tenant virtual data centers to a transit gateway to enable network connectivity into your {{site.data.keyword.cloud_notm}} Classic and Virtual Private Cloud (VPC) IaaS infrastructures, and your on-premises locations by using Direct Link connections. For more information, see [Using Transit Gateway to interconnect VMware as a Service with IBM Cloud services](/docs/vmware-service?topic=vmware-service-tgw-adding-connections).

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
:   The Dual Intel® 8260 Xeon® host profile (4 Sockets - 96 Cores, 1536 GB RAM) with 61 TB of VMware vSAN™ usable capacity is now available for Cloud Director sites.

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
:   This release announces the VMware as a Service Multitenant consumption model. VMware as a Service Multitenant provides a flexible, pay-per-use option to deploy virtual data centers on an IBM-managed Cloud Director site. You can get started quickly by selecting from on-demand or reserved pricing plans, and then add CPU, RAM, and storage as needed. Additionally, the Veeam Backup and Replication service is available for you to install to securely protect and provide a recovery option for your workloads. For more information, see [VMware as a Service overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).

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

Veeam Backup and Replication availability
:   The Veeam Backup and Replication service is now available by default for deployment with new and existing VMware as a Service instances. Service charges are incurred only if you choose to include the service in your order. For more information, see [Managing Veeam for VMware as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * The ordering flow for both VMware as a Service single-tenant Cloud Director sites and associated virtual data centers are now combined into a single ordering page.
   * The VMware as a Service **Resources** page now provides two tabbed views. In the first tab, all virtual data centers in the account are displayed. In the second tab, all authorized Cloud Director sites are displayed with the associated virtual data centers.
   * You can now access the VMware console from the virtual data center and Cloud Director site summary pages.
   * The **Add-on services** tab is available on instance details pages to easily manage the Veeam Backup and Replication service.

### 2 June 2023
{: #vmware-service-jun0223}
{: release-note}

IBM Cloud data center availability
:   (Updated on 30 June 2023) The **Frankfurt** region is now available to host your provider virtual data center. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

Accessing VMware as a Service REST APIs
:   You can now access VMware as a Service APIs through the {{site.data.keyword.cloud_notm}} Virtual Private Cloud. For more information, see [Using a virtual private endpoint](/docs/vmware-service?topic=vmware-service-virtual-private-endpoints).

Fast provisioning for virtual machines
:   Fast provisioning for virtual machines is now available for your virtual data centers. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

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
:   Documentation is now available describing how {{site.data.keyword.IBM}} maintains software currency for VMware and third-party software. For more information, see [Understanding IBM software currency policy](/docs/vmware-service?topic=vmware-service-policies).

### 10 February 2023
{: #vmware-service-feb1023}
{: release-note}

VMware currency
:   Infrastructure upgrade to VMware NSX-T 4.0 and VMware Cloud Director 10.4.1. This release resolves various issues, includes several deprecations, and introduces new features, such as API tokens and edge static routes. For more information, see [VMware Cloud Director 10.4.1 release notes](https://docs.vmware.com/en/VMware-Cloud-Director/10.4.1/rn/vmware-cloud-director-1041-release-notes/index.html){: external}.

Multiple clusters support
:   The limitation of one cluster per provider virtual data center (PVDC) is removed. For more information, see [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting).

Virtual data centers without edge
:   You can deploy virtual data centers (VDCs) without a network edge, which can help you save resources and costs by sharing an existing edge across multiple VDCs. This option is suitable for centralized networking administration and control over many VDCs. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

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
