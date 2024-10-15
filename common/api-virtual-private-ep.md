---

copyright:
  years:  2023, 2024

lastupdated: "2024-10-14"

keywords: network access policies, virtual private endpoints, virtual private gateway, VPE

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Using a Virtual Private Endpoint
{: #virtual-private-endpoints}

After you created your {{site.data.keyword.cloud}} Virtual Private Cloud (VPC) and you want to connect to {{site.data.keyword.vmware-service_notm}} APIs to create or manage your instance, you can create a Virtual Private Endpoint (VPE) in your VPC to access {{site.data.keyword.vcf-aas-full}} APIs within your VPC network.
{: shortdesc}

You can configure the VPE to use the IP addresses of your choice from a subnet within your VPC. VPEs are bound to a [VPE gateway](/docs/vpc?topic=vpc-about-vpe) and serve as an intermediary that enables your workload to interact with {{site.data.keyword.vcf-aas}}.

To connect to {{site.data.keyword.vcf-aas}} by using a VPE, you must use the {{site.data.keyword.vcf-aas}} API. You must access the VMware Solutions console through a public network from your VPC.
{: note}

## Before you begin
{: #vpe-prereqs}

You must complete the following before you target a VPE for {{site.data.keyword.vcf-aas}}.

- Ensure that you have [provisioned a Virtual Private Cloud](/docs/vpc?topic=vpc-getting-started).
- Ensure that you have reviewed [Planning for Virtual Private Endpoints](/docs/vpc?topic=vpc-planning-considerations).
- Ensure that [correct access controls](/docs/vpc?topic=vpc-acls-security-groups-vpn) are set for your VPE.
- Understand the [limitations](/docs/vpc?topic=vpc-limitations-vpe) of having a VPE.
- Ensure that you have [created](/docs/vpc?topic=vpc-ordering-endpoint-gateway) and understand how to [access](/docs/vpc?topic=vpc-accessing-vpe-after-setup) a VPE gateway.
- Understand how to [view details](/docs/vpc?topic=vpc-vpe-viewing-details-of-an-endpoint-gateway) of a VPE.

You may need to manually update VPE settings, specifically the IP address, during disaster recovery and business continuity actions.
{: important}

## Virtual Private Service Endpoints
{: #vpe-endpoints}

The following table lists regions where {{site.data.keyword.vcf-aas}} supports VPE. The table also provides {{site.data.keyword.vcf-aas}} endpoints supported from each region. You can connect to {{site.data.keyword.vcf-aas}} in another region using supported endpoints.

When connecting to a VPE using [CLI](/docs/vpc?topic=vpc-ordering-endpoint-gateway&interface=cli)
or [API](/docs/vpc?topic=vpc-ordering-endpoint-gateway&interface=api), you must specify the Cloud resource name of the region that you  use to connect to {{site.data.keyword.vcf-aas}}. Use the following table to locate the Cloud resource name of the target region.
{: note}

| Region     | Supported endpoints   | Cloud resource name    |
|------------|----------------------------------|------------------------|
| Dallas | `api.private.us-south.vmware.cloud.ibm.com` |`crn:v1:bluemix:public:vmware:us-south:::endpoint:api:private.us-south.vmware.cloud.ibm.com` |
| Frankfurt | `api.private.eu-de.vmware.cloud.ibm.com` | `crn:v1:bluemix:public:vmware:eu-de:::endpoint:api:private.eu-de.vmware.cloud.ibm.com` |
| London | `api.private.eu-gb.vmware.cloud.ibm.com` | `crn:v1:bluemix:public:vmware:eu-gb:::endpoint:api:private.eu-gb.vmware.cloud.ibm.com` |
| Tokyo | `api.private.jp-tok.vmware.cloud.ibm.com` | `crn:v1:bluemix:public:vmware:jp-tok:::endpoint:api:private.jp-tok.vmware.cloud.ibm.com` |
| Toronto | `api.private.ca-tor.vmware.cloud.ibm.com` | `crn:v1:bluemix:public:vmware:ca-tor:::endpoint:api:private.ca-tor.vmware.cloud.ibm.com` |
| Washington DC | `api.private.us-east.vmware.cloud.ibm.com` | `crn:v1:bluemix:public:vmware:us-east:::endpoint:api:private.us-east.vmware.cloud.ibm.com` |
{: caption="Private endpoints for interacting with VCF as a Service APIs over the IBM Cloud private network" caption-side="bottom"}
