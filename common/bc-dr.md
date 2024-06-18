---

copyright:
  years: 2022, 2024

lastupdated: "2024-04-09"

keywords: HA for vmware service, DR for vmware service, high availability for vmware service, disaster recovery for vmware service, failover for vmware service, BC for vmware service, DR for vmware service, business continuity for vmware service, disaster recovery for vmware service

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Understanding business continuity and disaster recovery for {{site.data.keyword.vcf-aas}}
{: #bc-dr}

[Disaster recovery](#x2113280){: term} involves a set of policies, tools, and procedures for returning a system, an application, or an entire data center to full operation after a catastrophic interruption. It includes procedures for copying and storing an installed system's essential data in a secure location, and for recovering that data to restore normalcy of operation.
{: shortdesc}

## Responsibilities
{: #bc-dr-responsibilities}

For more information about responsibility ownership for using {{site.data.keyword.cloud}} products between {{site.data.keyword.IBM}} and the customer, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).

For more information about your responsibilities when using {{site.data.keyword.vmware-service_notm}}, see [Understanding your responsibilities when using {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-understand-responsib).

## Disaster recovery strategy
{: #bc-dr-strategy}

{{site.data.keyword.cloud_notm}} has [business continuity](#x3026801){: term} plans in place to provide for the recovery of services within hours if a disaster occurs. You are responsible for your data backup and associated recovery of your content.

{{site.data.keyword.vcf-aas-full}} provides mechanisms to protect your data and restore service functions. Business continuity plans are in place to achieve targeted [recovery point objective](#x3429911){: term} (RPO) and [recovery time objective](#x3167918){: term} (RTO) for the service. The following table outlines the targets for {{site.data.keyword.vcf-aas}}.

| Disaster recovery objective | Target value | Method |
|:--------------------------- |:------------ |:------ |
| RPO | 24 h | Use a backup provider such as Veeam® Backup and Recovery to store periodic backups of your workload. |
| RPO | Minutes | Use a replication provider such as Veeam to replicate your workload to another location. |
| RTO | Minutes to hours | The recovery time objective depends on the storage medium that is used for your backups and on how long it takes for your workload to be ready from a cold start. |
{: caption="Table 1. RPO and RTO for {{site.data.keyword.vcf-aas}}" caption-side="bottom"}

## Locations
{: #bc-dr-locations}

For more information about service availability within regions and data centers, see [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).
