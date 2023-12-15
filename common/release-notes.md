---

copyright:
  years: 2022, 2023

lastupdated: "2023-12-15"

keywords: release notes, what's new in vmware service, what is new, new features, vmware release notes, vmware service

subcollection: vmware-service

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.vmware-service_short}}
{: #vmware-service-relnotes}

Use these release notes to learn about the most recent updates to {{site.data.keyword.vmware-service_full}}, including new features, component updates, usability enhancements, and bug fixes.
{: shortdesc}

## 2023
{: #vmware-service-year-2023}

### 15 December 2023
{: #vmware-service-dec2023}
{: release-note}

Cloud-to-cloud migration to VMware as a Service
:   You can now use cloud-to-cloud connections to migrate {{site.data.keyword.vmwaresolutions_short}} Shared instances to {{site.data.keyword.vmware-service_short}}. You can also use cloud-to-cloud connections to migrate workloads from single-tenant and multitenant {{site.data.keyword.vmware-service_short}} instances to another {{site.data.keyword.vmware-service_short}} instance. For more information, see [Creating and deleting VMware as a Service pairings](/docs/vmware-service?topic=vmware-service-vcda-creating-deleting-vmaas-pairing).

vSAN host profile updates
:   The Dual Intel® 8260 Xeon® host profile (4 Sockets - 96 Cores, 1536 GB RAM) with 61 TB of VMware vSAN™ usable capacity is now available for Cloud Director sites.

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

New documentation
:   A number of solution tutorials are now available under the **Tutorials** section of the {{site.data.keyword.vmware-service_short}} documentation. These tutorials provide step-by-step instructions about using VMware as a Service to implement common patterns based on best practices.

### 17 November 2023
{: #vmware-service-nov2023}
{: release-note}

Migrating virtual machines to VMware as a Service
:   The VMware Cloud Director Availability (VCDA) service is now available as a cost-effective solution to easily migrate your VMware vCenter Server® or on-premises workloads to the VMware as a Service single-tenant consumption model. Use enterprise-level VCDA to migrate virtual machines over a secure public internet connection at no cost. For more information, see [VMware Cloud Director Availability for VMware as a Service overview](/docs/vmware-service?topic=vmware-service-tenant-vcda).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

Documentation updates and enhancements
:   The table of contents is updated for a more streamlined user experience.

### 20 October 2023
{: #vmware-service-oct2023}
{: release-note}

VMware as a Service Multitenant
:   This release announces the {{site.data.keyword.vmware-service_short}} Multitenant consumption model. {{site.data.keyword.vmware-service_short}} Multitenant provides a flexible, pay-per-use option to deploy virtual data centers on an IBM-managed Cloud Director site. You can get started quickly by selecting from on-demand or reserved pricing plans, and then add CPU, RAM, and storage as needed. Additionally, the Veeam® Backup and Replication service is available for you to install to securely protect and provide a recovery option for your workloads. For more information, see [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).

REST API updates
:   The [VMware as a Service API](/apidocs/vmware-service) is updated to provide support for {{site.data.keyword.vmware-service_short}} Multitenant. For more information, see [VMware as a Service API change log](/docs/vmware-service?topic=vmware-service-vmware-service-api-change-log#vmware-service-20-october-2023).

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements.

### 22 September 2023
{: #vmware-service-sep2223}
{: release-note}

IBM Cloud data center availability
:   {{site.data.keyword.vmware-service_short}} expands global presence and now supports the **Washington DC** region to host your provider virtual data center. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

SAP-certified provider virtual data centers
:   {{site.data.keyword.vmware-service_short}} now supports SAP® workloads that use the new SAP bare metal server profiles. You can reliably run your mission-critical SAP workloads and scenarios on a scalable, compliant, and enterprise-proven VMware® platform.
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
:   The Veeam® Backup and Replication service is now available by default for deployment with new and existing {{site.data.keyword.vmware-service_short}} instances. Service charges are incurred only if you choose to include the service in your order. For more information, see [Managing Veeam for VMware as a Service](/docs/vmware-service?topic=vmware-service-tenant-veeam).

User interface updates and enhancements
:   The user interface is updated and provides the following enhancements.

   * The ordering flow for both {{site.data.keyword.vmware-service_short}} single-tenant Cloud Director sites and associated virtual data centers are now combined into a single ordering page.
   * The {{site.data.keyword.vmware-service_short}} **Resources** page now provides two tabbed views. In the first tab, all virtual data centers in the account are displayed. In the second tab, all authorized Cloud Director sites are displayed with the associated virtual data centers.
   * You can now access the VMware console from the virtual data center and Cloud Director site summary pages.
   * The **Add-on services** tab is available on instance details pages to easily manage the Veeam Backup and Replication service.

### 2 June 2023
{: #vmware-service-jun0223}
{: release-note}

IBM Cloud data center availability
:   (Updated on 30 June 2023) The **Frankfurt** region is now available to host your provider virtual data center. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy#tenant-plan-deploy-locations).

Accessing {{site.data.keyword.vmware-service_short}} REST APIs
:   You can now access {{site.data.keyword.vmware-service_short}} APIs through the {{site.data.keyword.cloud_notm}} Virtual Private Cloud. For more information, see [Using a virtual private endpoint](/docs/vmware-service?topic=vmware-service-virtual-private-endpoints).

Fast provisioning for virtual machines
:   Fast provisioning for virtual machines is now available for your virtual data centers. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

VMware currency
:   This release provides infrastructure upgrades to VMware NSX-T™ 4.1 and VMware ESXi™ 7.0U3L.

User interface updates and enhancements
:   You can check the prices for {{site.data.keyword.vmware-service_short}} without having to sign in to {{site.data.keyword.cloud_notm}}. However, you might have limited access to some sections of the ordering pages. To place an order, or for a complete access to the ordering pages, you must log in to {{site.data.keyword.cloud_notm}}.

### 5 May 2023
{: #vmware-service-may0523}
{: release-note}

vSAN storage availability
:   You can now select vSAN storage with optional NFS storage for your instance order in locations with 25 GbE availability. For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).

REST APIs
:   REST APIs are now available for all {{site.data.keyword.vmware-service_short}} capabilities. For more information, see [VMware as a Service API](/apidocs/vmware-service).

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
:   You can now create PVDCs across three data centers in the region. For more information, see [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering) and [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

Add PVDC with new cluster
:   Adding multiple PVDCs with new clusters is now supported, with a limitation of one cluster per PVDC. For more information, see [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

IAM enablement
:   VMware Cloud Director SSO is enabled with {{site.data.keyword.cloud_notm}} IAM (Identity and Access Management) for new sites. You can also enable IAM for existing sites. After you integrate your site with IAM, you can use single sign-on to log in to the VMware Cloud Director console from the VMware Solutions console. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmware-service?topic=vmware-service-iam-integration).

## 2022
{: #vmware-service-year-2022}

### 14 November 2022
{: #vmware-service-nov1422}
{: release-note}

{{site.data.keyword.vmware-service_short}} released
:   {{site.data.keyword.vmware-service_short}} is released! For more information, see [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).
