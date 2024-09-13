---

copyright:

  years: 2022, 2024

lastupdated: "2024-09-13"

keywords: vmware service overview, vmware cloud foundation as a service, vmware cloud foundation as a service overview, vmware cloud foundation as a service introduction, VCF as a Service

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}
{:video: .video}

# {{site.data.keyword.vcf-aas}} overview
{: #vmware-aas-overview}

{{site.data.keyword.vmware-service_full}} provides the VMware Cloud Director™ platform as either a dedicated or shared managed service. {{site.data.keyword.IBM}} performs the configuration, hosting, operations, and lifecycle management of the VMware® by Broadcom software so you can quickly deploy your VMware-based cloud computing environments. Compute resources are available as either dedicated or multitenant hosts that use {{site.data.keyword.cloud_notm}} bare metal servers. Dedicated single-tenant VMware sites provide extra isolation and support multiple host configuration options to support flexible workload requirements.
{: shortdesc}

{{site.data.keyword.vcf-aas-full}} multitenant instances are deployed to all supported regions by {{site.data.keyword.IBM_notm}}. Create your virtual data centers (VDCs) on the {{site.data.keyword.IBM_notm}} managed infrastructure. {{site.data.keyword.vcf-aas}} single-tenant instances are provisioned and managed by your organization.

For complete billing details for both multitenant and single-tenant models, see the [**About** tab](https://cloud.ibm.com/vmware/vmware_as_a_service/provision/vdc_mt) on the {{site.data.keyword.vmware-service_short}} provision page.
{: note}

Find out more about the {{site.data.keyword.vcf-aas}} instance models in the following video.

![Introducing IBM Cloud for {{site.data.keyword.vmware-service_notm}}](https://cdnapisec.kaltura.com/html5/html5lib/v2.101/mwEmbedFrame.php/p/1773841/uiconf_id/27941801/entry_id/1_mrpl7ue5?wid=_1773841&iframeembed=true&entry_id=1_mrpl7ue5){: video output="iframe" data-script="none" id="intromediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

## {{site.data.keyword.vcf-aas}} single-tenant
{: #vmware-aas-overview-st}

The {{site.data.keyword.vcf-aas}} single-tenant consumption model provides the option to deploy managed VMware environments with a dedicated infrastructure. You can select from a choice of bare metal servers and storage infrastructure components to create a single-tenant VMware site. You manage the capacity of the infrastructure.

The combination of the single-tenant infrastructure and a software stack that includes VMware ESXi™, VMware vCenter®, VMware NSX-T™, and Cloud Director is called a site. Sites are the single-tenant VMware platform that is used to host one or more VMware VDCs. VMware VDCs are used to deploy VMware workloads to create virtualized networking, and to connect to external networks that include the public internet and the {{site.data.keyword.IBM_notm}} private network. You can start with as little as two dedicated bare metal servers to deploy or migrate existing VMware workloads into a VMware Cloud Director VDC.

For {{site.data.keyword.vcf-aas}} single-tenant, you first create the dedicated Cloud Director site and then you create the VDCs after the site is ready. Find out more about ordering a dedicated single-tenant Cloud Director site in the following video.

![IBM Cloud for VMware Cloud Foundation as a Service - How to create a Single Tenant Site](https://www.kaltura.com/p/1773841/sp/177384100/embedIframeJs/uiconf_id/27941801/partner_id/1773841?iframeembed=true&entry_id=1_drcc4jz0){: video output="iframe" data-script="none" id="stmediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

## {{site.data.keyword.vcf-aas}} multitenant
{: #vmware-aas-overview-mt}

The {{site.data.keyword.vcf-aas}} multitenant consumption model provides the same capabilities and experience as the single-tenant model. With {{site.data.keyword.vcf-aas}} multitenant, your workloads share the VMware site platform of infrastructure and VMware components. VMware workloads across different Cloud accounts are securely isolated by VMware Cloud Director virtualization of networking, storage, CPU, and RAM.

For {{site.data.keyword.vcf-aas}} multitenant, you start by creating the multitenant VDC with a choice of on-demand pay-as-you-go pricing or reserved pricing plans. IBM Operations manages the physical CPU, RAM, and storage infrastructure capacity. Find out more about ordering a multitenant VDC in the following video.

![IBM Cloud for VCF as a Service-How to create a Multi Tenant VDC](https://www.kaltura.com/p/1773841/sp/177384100/embedIframeJs/uiconf_id/27941801/partner_id/1773841?iframeembed=true&entry_id=1_5tjb9dfs){: video output="iframe" data-script="none" id="mtmediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

## {{site.data.keyword.vcf-aas}} features
{: #vmware-aas-overview-features}

The {{site.data.keyword.vcf-aas}} single-tenant and multitenant models share the following features:

* The VMware Cloud Director instance that you log in to provides a 99.99% availability SLA.
* Unique provider-managed encryption keys per instance with encrypted VMware storage profiles.
* Single sign-on (SSO) with role-based authentication and authorization from {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) to VMware Cloud Director.
* Improved provisioning speed, availability, and resilience.
* Regional-level High Availability through creating VMware Cloud Director VDCs in multiple data centers in the same region.
* VMware infrastructure health and patching is managed by {{site.data.keyword.IBM_notm}} Operations up through the hypervisor.
* Full compatibility to run existing VMware workloads. Migration of existing {{site.data.keyword.cloud_notm}}, on-premises or other workloads are fully supported.
* Create and delete VDCs to deploy VMware workload vApps and virtual machines in VMware Cloud Director.
* Public-only or private-only networking for management connectivity.
* Public and private or private-only networking for workload connectivity.
* Secure interconnectivity through {{site.data.keyword.tg_full_notm}}
* Optional data protection through the Veeam® Backup service.
* Optional VM and vApp migration and protection through the VMware Cloud Director Availability service.

### {{site.data.keyword.vcf-aas}} single-tenant features
{: #vmware-aas-overview-features-st}

For single-tenant instances, first define a VMware environment by provisioning a {{site.data.keyword.vcf-aas}} single-tenant Cloud Director site. Then, create {{site.data.keyword.vcf-aas}} single-tenant VDCs to deploy your workloads.

The {{site.data.keyword.vcf-aas}} single-tenant consumption model provides the following features:

* The highest level of isolation, control, and consistency of the underlying VMware environment.
* Each {{site.data.keyword.vcf-aas}} single-tenant instance contains the following VMware components:
   * Dedicated VMware ESXi hosts
   * Dedicated VMware vCenter
   * Multiple performance options for attached vSAN™ and Network File Storage (NFS v3)
   * Dedicated VMware NSX-T with dedicated networking
   * Dedicated VMware Cloud Director
* Right-size and scale of the VMware environment:
   * Add and remove VMware Cloud Director PVDCs
   * Add and remove VMware vCenter clusters
   * Add and remove hosts per VMware vCenter cluster
   * Add and remove storage per VMware vCenter cluster
* Option to connect VDCs to the public and IBM private networks through network edges.
* Monthly billing for the dedicated infrastructure and components.

### {{site.data.keyword.vcf-aas}} multitenant features
{: #vmware-aas-overview-features-mt}

For multitenant instances, create a VDC that deploys on an existing VMware multitenant infrastructure that is created and managed by {{site.data.keyword.IBM_notm}}.

The {{site.data.keyword.vcf-aas}} multitenant consumption model provides the following features:

* Shares resources with others by using a balanced VMware environment profile to support a wide range of needs.
* Pay-per-use consumption model:
   * On-demand hourly pricing based on resource usage. Resources are allocated as needed.
   * Reserved monthly pricing based on the allocation size. Resources are pre-allocated and guaranteed.
* Option to connect VDCs to the public and IBM private networks through network edges.
* Billing is determined by the consumption of virtualized CPU (vCPU), RAM, and networking.
* Add or remove vCPU and RAM limits as needed.

## Billing specifications for {{site.data.keyword.vcf-aas}}
{: #vmware-aas-overview-specs}

{{site.data.keyword.vcf-aas}} single-tenant instances incur charges for the following components.

* NFS size and performance tiers used
* Host type and counts used
* Egress to public networking
* Ingress to private networking (optional)
* Networking edge types and counts
* Veeam Backup service (optional)
* VMware Cloud Director Availability for Disaster Recovery (optional)

{{site.data.keyword.vcf-aas}} multitenant instance charges are based on either the on-demand or reserved pricing models.

## Related links
{: #vmware-aas-overview-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering {{site.data.keyword.vcf-aas}} virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Ordering {{site.data.keyword.vcf-aas}} Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
