---

copyright:
  years:  2023

lastupdated: "2023-12-14"

keywords: change log for VMware as a Service API, updates to VMware as a Service API

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vmware-service_short}} API change log
{: #vmware-service-api-change-log}

In this change log, you can learn about the most recent changes, improvements, and updates for the [{{site.data.keyword.vmware-service_short}} API](/apidocs/vmware-service). The change log lists the changes that were made, ordered by the date they were released. Changes to existing API versions are compatible with existing client applications.

## 20 October 2023
{: #vmware-service-20-october-2023}

* Added support for director site instance `type` and pvdc `provider_type` to distinguish between multitenant and single-tenant. For more information, see [Get a director site instance](/apidocs/vmware-service#get-director-site) and [List director site instances](/apidocs/vmware-service#list-director-sites).
* Added support for including services when you create a director site instance and retrieve a director site instance. For more information, see [Create a director site instance](/apidocs/vmware-service#create-director-sites) and [Get a director site instance](/apidocs/vmware-service#get-director-site).
* Added support for creating additional cluster. For more information, see [Create a cluster](/apidocs/vmware-service#create-director-sites-pvdcs-clusters).
* Added support for updating a virtual data center (VDC) instance configuration. Currently, fast provisioning configuration is supported. For more information, see [Update a virtual data center](/apidocs/vmware-service#update-vdc).
* Added support for retrieving `rhel_vm_activation_key` of a director site instance. For more information, see [Get a director site instance](/apidocs/vmware-service#get-director-site) and [List director site instances](/apidocs/vmware-service#list-director-sites).

## 5 May 2023
{: #vmware-service-5-may-2023}

REST APIs are now available for all {{site.data.keyword.vmware-service_full}} capabilities. API version 1.0.0 is supported. For more information, see [VMware as a Service API](/apidocs/vmware-service).
