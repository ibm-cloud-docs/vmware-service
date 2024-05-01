---

copyright:
  years:  2023, 2024

lastupdated: "2024-05-01"

keywords: change log for VMware Cloud Foundation as a Service API, updates to VCF as a Service API

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vcf-aas}} API change log
{: #vmware-service-api-change-log}

In this change log, you can learn about the most recent changes, improvements, and updates for the [VMware Cloud Foundation as a Service API](/apidocs/vmware-service). The change log lists the changes that were made, ordered by the date they were released. Changes to existing API versions are compatible with existing client applications.

## 15 March 2024
{: #vmware-service-15-march-2024}

* Added support for enabling and disabling the VMware Cloud Director Availability (VCDA) service for VMware Cloud Director sites. For more information, see [Enable or disable Veeam on a Cloud Director site](/apidocs/vmware-service#enable-veeam-on-pvdcs-list).
* Added support for enabling and disabling the Veeam® service for Cloud Director sites. For more information, see [Enable or disable VCDA on a Cloud Director site](/apidocs/vmware-service#enable-vcda-on-data-center).

## 9 February 2024
{: #vmware-service-9-february-2024}

* Added VCDA support for Cloud Director sites. For more information, see:
   * [Create a VCDA cloud-to-cloud connection](/apidocs/vmware-service#create-director-sites-vcda-c2c-connection)
   * [Update VCDA connection allowlist](/apidocs/vmware-service#update-director-sites-vcda-connection-endpoints)
   * [Delete a VCDA cloud-to-cloud connection](/apidocs/vmware-service#delete-director-sites-vcda-c2c-connection)
* Added private-only configuration support for Cloud Director sites. For more information, see [Create a Cloud Director site instance](/apidocs/vmware-service#create-director-sites).
* Added OpenID Connect (OIDC) configuration support for Cloud director sites. For more information, see:
   * [Get an OIDC configuration](/apidocs/vmware-service#get-oidc-configuration)
   * [Set an OIDC configuration](/apidocs/vmware-service#set-oidc-configuration)
* Added {{site.data.keyword.tg_full_notm}} support to create and delete Transit Gateways for a virtual data center (VDC) edge. For more information, see:
   * [Add IBM Transit Gateway connections to edge](/apidocs/vmware-service#add-transit-gateway-connections)
   * [Remove IBM Transit Gateway connections from edge](/apidocs/vmware-service#remove-transit-gateway-connections)

## 20 October 2023
{: #vmware-service-20-october-2023}

* Added support for director site instance `type` and pvdc `provider_type` to distinguish between multitenant and single-tenant. For more information, see [Get a director site instance](/apidocs/vmware-service#get-director-site) and [List director site instances](/apidocs/vmware-service#list-director-sites).
* Added support for including services when you create a director site instance and retrieve a director site instance. For more information, see [Create a director site instance](/apidocs/vmware-service#create-director-sites) and [Get a director site instance](/apidocs/vmware-service#get-director-site).
* Added support for creating additional cluster. For more information, see [Create a cluster](/apidocs/vmware-service#create-director-sites-pvdcs-clusters).
* Added support for updating a VDC instance configuration. Currently, fast provisioning configuration is supported. For more information, see [Update a virtual data center](/apidocs/vmware-service#update-vdc).
* Added support for retrieving `rhel_vm_activation_key` of a director site instance. For more information, see [Get a director site instance](/apidocs/vmware-service#get-director-site) and [List director site instances](/apidocs/vmware-service#list-director-sites).

## 5 May 2023
{: #vmware-service-5-may-2023}

REST APIs are now available for all VMware as a Service capabilities. API version 1.0.0 is supported. For more information, see [VMware as a Service API](/apidocs/vmware-service).
