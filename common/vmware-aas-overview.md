---

copyright:

  years: 2022, 2023

lastupdated: "2023-01-09"

keywords: vmware service overview, vmware as a service, vmware as a service overview, vmware as a service introduction

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vmware-service_short}} overview
{: #vmware-aas-overview}

{{site.data.keyword.vmware-service_full}} provides the VMware Cloud Director platform as a managed service. IBM performs the configuration, hosting, operations, and lifecycle management of the VMware software so you can quickly deploy your VMware-based cloud computing environments.

Compute resources are available as dedicated hosts, by using IBM Cloud Bare Metal servers, with multiple host configurations available to address various workload requirements.
{: shortdesc}

## {{site.data.keyword.vmware-service_short}} features and functions
{: #vmware-aas-overview-features}

The {{site.data.keyword.vmware-service_short}} offering has the following features:

* VMware stack management up to the hypervisor level
   * IBM-managed infrastructure
   * IBM-managed VMware components and services
* Dedicated hosts and multiple host profiles for creating VMware vCenter clusters
* Multiple performance options for attached Network File Storage (NFS v3)
* Monthly billing
* Unique provider-managed encryption keys per instance with encrypted VMware storage profiles
* Single sign-on (SSO) with role-based authentication and authorization from IBM Cloud IAM (Identity and Access Management) to VMware Cloud Director
* Improved provisioning speed, availability, and resilience
* Regional-level High Availability through creating VMware Cloud Director provider virtual data centers (provider VDCs) and vCenter clusters in multiple data centers in the same region.
* Full compatibility to run existing VMware workloads. Migration of existing IBM Cloud, on-premises or other workloads are fully supported.
* Each {{site.data.keyword.vmware-service_short}} instance contains the following VMware components:
   * Dedicated VMware ESXi hosts
   * Dedicated VMware vCenter
   * Dedicated VMware NSX-T with dedicated networking
   * Dedicated VMware Cloud Director
* Right-size and scale the VMware environment
   * Add and remove hosts per VMware vCenter cluster
   * Add and remove storage per VMware vCenter cluster
   * Add and remove VMware vCenter clusters
   * Add and remove VMware Cloud Director provider VDC
* Create and delete virtual data centers to deploy VMware workload vApps and VMs in VMware Cloud Director

## Billing specifications for {{site.data.keyword.vmware-service_short}}
{: #vmware-aas-overview-specs}

{{site.data.keyword.vmware-service_short}} instances incur charges for the following components:

* NFS Storage size and performance tiers used
* Host type and counts used
* Egress public networking
* Networking edge types and counts

## {{site.data.keyword.vmware-service_short}} locations
{: #vmware-aas-overview-locations}

This offering is available in the **Dallas** region.

## Related links
{: #vmware-aas-overview-links}

* [Ordering {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud_notm}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
* [Deleting {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-deleting)
