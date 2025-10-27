---

copyright:
  years: 2025
lastupdated: "2025-10-24"

keywords: data portability, VCF as a Service, IBM Cloud for VMware Cloud Foundation as a Service

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Understanding data portability for {{site.data.keyword.vmware-service_short}}
{: #data-portability}

{{site.data.content.vms-deprecated-note}}

Data portability involves a set of tools and procedures that enable you to export the digital artifacts that are needed to implement similar workload and data processing on different service providers or on-premises software. It includes procedures for copying and storing the service customer content, including the related configuration that is used by the service to store and process the data, in your location.
{: shortdesc}

## Responsibilities
{: #data-portability-responsibilities}

{{site.data.keyword.cloud}} services provide interfaces and instructions to guide you through the process of copying and storing service customer content, including the related configuration, in your selected location.

You're responsible for the use of the exported data and configuration for data portability to other infrastructures, which includes:

- The planning and execution for setting up alternative infrastructure on different cloud providers or on-premises software that provide similar capabilities to the {{site.data.keyword.IBM_notm}} services.
- The planning and execution for the porting of the required application code on the alternative infrastructure, including the adaptation of your application code, deployment automation, and so on.
- The conversion of the exported data and configuration to the format required by the alternative infrastructure and adapted applications.

For more information about your responsibilities for {{site.data.keyword.vmware-service_notm}}, see [Understanding your responsibilities when you use VCF as a Service](/docs/vmware-service?topic=vmware-service-vmaas-understand-responsib).

## Data export procedures
{: #data-portability-procedures}

Data portability in {{site.data.keyword.vmware-service_short}} is accomplished by using the VMware Cloud Director™ Availability (VCDA) product. For more information about VCDA and how to migrate workloads and data to an alternative infrastructure site, see [VMware Cloud Director Availability Migration - White Paper](https://www.vmware.com/docs/vmware-cloud-director-availability-migration){: external}.

## Exported data formats
{: #data-portability-data-formats}

The exported data format is set and controlled by the VMware Cloud Director Availability product. For more information, see [VMware Cloud Director Availability - Migration White Paper](https://www.vmware.com/docs/vmware-cloud-director-availability-migration){: external}.

## Data ownership
{: #data-portability-ownership}

All exported data is classified as customer content. Apply the full customer ownership and licensing rights, as stated in the [IBM Cloud Service Agreement](https://www.ibm.com/support/customer/csol/terms/?id=Z126-6304_WS){: external}.
