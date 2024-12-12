---

copyright:
  years: 2022, 2024

lastupdated: "2024-12-11"

keywords: HA for vmware service, high availability for vmware service

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Understanding high availability for {{site.data.keyword.vcf-aas}}
{: #ha}

[High availability](#x2284708){: term} (HA) is a core discipline in an IT infrastructure to keep your apps up and running, even after a partial or full site failure. The main purpose of high availability is to eliminate potential points of failures in an IT infrastructure.
{: shortdesc}

## Responsibilities
{: #ha-responsibilities}

For more information about responsibility ownership for using {{site.data.keyword.cloud}} products between {{site.data.keyword.IBM}} and the customer, see [Shared responsibilities for using {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).

For more information about your responsibilities when using {{site.data.keyword.vcf-aas-full}}, see [Understanding your responsibilities when using {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-understand-responsib).

## What level of availability do I need?
{: #ha-level}

You can achieve high availability on different levels in your IT infrastructure and within different components of your workload. The level of availability that is best for you depends on several factors, such as your business requirements, the service level agreements (SLAs) that you have with your customers, and the resources that you want to expend.

## What level of availability does {{site.data.keyword.cloud_notm}} offer?
{: #ha-service}

Service level objectives (SLOs) describe the design points that the {{site.data.keyword.cloud_notm}} services are engineered to meet. {{site.data.keyword.vcf-aas}} is designed to achieve the following availability target.

| Availability target | Target value | Method |
|:------------------- |:------------ | :----- |
| Availability % | 99.9% | Single instance in a single zone. Your workload is restarted on other hosts if a host failure occurs. |
| Availability % | 99.99% | Multiple instances that are distributed across multiple zones or regions. Workload is not automatically restarted across zones or regions, but must be designed and implemented for continuous availability or warm standby between zones or regions. |
{: caption="SLO for {{site.data.keyword.vcf-aas}}" caption-side="bottom"}

The SLO is not a warranty and {{site.data.keyword.IBM_notm}} will not issue credits for failure to meet an objective. Refer to the SLAs for commitments and credits that are issued for failure to meet any committed SLAs. For more information, see [Service Level Agreements (SLAs)](/docs/overview?topic=overview-slas).

A complete business continuity plan also addresses cases such as regional or site failure; and events such as corruption, malware, and user error. Consider the use of [replication and backup](/docs/vmware-service?topic=vmware-service-bc-dr) as part of your planning.

## Locations
{: #ha-locations}

For more information about service availability within regions and data centers, see [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).
