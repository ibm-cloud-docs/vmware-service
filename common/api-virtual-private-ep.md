---

copyright:
  years:  2023

lastupdated: "2023-05-26"

keywords: network access policies, virtual private endpoints, virtual private gateway, VPE

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Using a virtual private endpoint
{: #virtual-private-endpoints}

After you created your {{site.data.keyword.cloud}} Virtual Private Cloud (VPC) and you want to connect to {{site.data.keyword.vmware-service_short}} APIs to create or manage your instance, you can create a Virtual Private Endpoint (VPE) in your VPC to access {{site.data.keyword.vmware-service_short}} APIs within your VPC network.
{: shortdesc}

You can configure the VPE to use the IP addresses of your choice from a subnet within your VPC. VPEs are bound to a [VPE gateway](/docs/vpc?topic=vpc-about-vpe) and serve as an intermediary that enables your workload to interact with {{site.data.keyword.vmware-service_short}}.

To connect to {{site.data.keyword.vmware-service_short}} by using a VPE, you must use the {{site.data.keyword.vmware-service_short}} API. You must access the VMware Solutions console through a public network from your VPC.
{: note}

## Before you begin
{: #vpe-prereqs}

You must complete the following before you target a VPE for {{site.data.keyword.vmware-service_short}}.

- Ensure that you have [provisioned a Virtual Private Cloud](/docs/vpc?topic=vpc-getting-started).
- Ensure that you have reviewed [planning for Virtual Private Endpoints](/docs/vpctopic=vpc-planning-considerations).
- Ensure that [correct access controls](/docs/vpc?topic=vpc-vpe-configuring-acls) are set for your VPE.
- Understand the [limitations](/docs/vpc?topic=vpc-limitations-vpe) of having a VPE.
- Ensure that you have [created](/docs/vpc?topic=vpc-ordering-endpoint-gateway) and understand how to [access](/docs/vpc?topic=vpc-accessing-vpe-after-setup) a VPE gateway.
- Understand how to [view details](/docs/vpc?topic=vpc-vpe-viewing-details-of-an-endpoint-gateway) of a VPE.

You may need to manually update VPE settings, specifically the IP address, during disaster recovery and business continuity actions.
{: important}

## Virtual Private Service Endpoints
{: #vpe-endpoints}

The following table lists regions where {{site.data.keyword.vmware-service_short}} supports VPE. The table also provides {{site.data.keyword.vmware-service_short}} endpoints supported from each region. You can connect to {{site.data.keyword.vmware-service_short}} in another region using supported endpoints.

When connecting to a VPE using [CLI](/docs/vpc?topic=vpc-ordering-endpoint-gateway#vpe-ordering-cli)
or [API](/docs/vpc?topic=vpc-ordering-endpoint-gateway#vpe-ordering-api), you must specify the Cloud resource name of the region that you  use to connect to {{site.data.keyword.vmware-service_short}}. Use the following table to locate the Cloud resource name of the target region.
{: note}

| Region     | Supported endpoints   | Cloud resource name    |
|------------|----------------------------------|------------------------|
| Dallas | `api.private.us-south.vmware.cloud.ibm.com` |`crn:v1:bluemix:public:vmware:us-south:::endpoint:api:private.us-south.vmware.cloud.ibm.com` |
{: caption="Table 1. Private endpoints for interacting with {{site.data.keyword.vmware-service_short}} APIs over the IBM Cloud private network" caption-side="bottom"}
