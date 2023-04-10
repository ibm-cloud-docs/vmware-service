---

copyright:
  years: 2022, 2023

lastupdated: "2023-04-07"

keywords: release notes, what's new in vmware service, what is new, new features, vmware release notes, vmware service

subcollection: vmware-service

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

{:release-note: data-hd-content-type='release-note'}

# Release notes for {{site.data.keyword.vmware-service_short}}
{: #vmware-service-relnotes}

Use these release notes to learn about the most recent updates to {{site.data.keyword.vmware-service_full}}, including new features, component updates, usability enhancements, and bug fixes.
{: shortdesc}

## 2023
{: #vmware-service-year-2023}

### 7 April 2023
{: #vmware-service-april-2023}
{: release-note}

Mirrored M.2 disk availability
:   VMware® 7.0u3 ESXi™ server host boot disks are now provisioned as mirrored M.2 disks.

### 10 March 2023
{: #vmware-service-march-2023}
{: release-note}

Data center support for 25 GbE
:   Beginning with {{site.data.keyword.vmware-service_short}} 1.3, you can select a data center with networking speed of either 10 GbE or 25 GbE.

User interface updates and enhancements
:   The user interface is updated with various message and tooltip enhancements. Additionally, **Dark** mode is now enabled.

IBM software currency policy
:   Documentation is now available describing how {{site.data.keyword.IBM}} maintains software currency for VMware and third-party software. For more information, see [Understanding IBM software currency policy](/docs/vmware-service?topic=vmware-service-policies).

### 10 February 2023
{: #vmware-service-february-2023}
{: release-note}

VMware currency
:   Beginning with {{site.data.keyword.vmware-service_short}} 1.2, the infrastructure is upgraded to VMware NSX-T™ 4.0 and VMware Cloud Director 10.4.1. This release resolves various issues, includes several deprecations, and introduces new features, such as API tokens and edge static routes. For more information, see [VMware Cloud Director 10.4.1 release notes](https://docs.vmware.com/en/VMware-Cloud-Director/10.4.1/rn/vmware-cloud-director-1041-release-notes/index.html){: external}.

Multiple clusters support
:   The limitation of one cluster per provider virtual data center (PVDC) is removed. For more information, see [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting).

Virtual data centers without edge
:   You can deploy virtual data centers (VDCs) without a network edge, which can help you save resources and costs by sharing an existing edge across multiple VDCs. This option is suitable for centralized networking administration and control over many VDCs. For more information, see [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding).

### 18 January 2023
{: #vmware-service-january-2023}
{: release-note}

Multizone support
:   Beginning with {{site.data.keyword.vmware-service_short}} 1.1, you can create PVDCs across three data centers in the region. For more information, see [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering) and [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

Add PVDC with new cluster
:   Adding multiple PVDCs with new clusters is now supported, with a limitation of one cluster per PVDC. For more information, see [Adding and deleting PVDCs](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting).

IAM enablement
:   VMware Cloud Director SSO is enabled with {{site.data.keyword.cloud_notm}} IAM (Identity and Access Management) for new sites. You can also enable IAM for existing sites. After you integrate your site with IAM, you can use single sign-on to log in to the VMware Cloud Director console from the VMware Solutions console. For more information, see [VMware Cloud Director single sign-on with IBM Cloud IAM](/docs/vmware-service?topic=vmware-service-iam-integration).

## 2022
{: #vmware-service-year-2022}

### 14 November 2022
{: #vmware-service-november-2022}
{: release-note}

{{site.data.keyword.vmware-service_short}} released
:   {{site.data.keyword.vmware-service_short}} is released! For more information, see [{{site.data.keyword.vmware-service_short}} overview](/docs/vmware-service?topic=vmware-service-vmware-aas-overview).
