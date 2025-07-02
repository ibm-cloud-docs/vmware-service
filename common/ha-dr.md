---

copyright:
  years: 2025
lastupdated: "2025-07-02"

keywords: HA for VCF as a Service, DR for VCF as a Service, VCF as a Service recovery time objective, VCF as a Service recovery point objective

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Understanding high availability and disaster recovery for VCF as a Service
{: #ha-dr}



[High availability](#x2284708){: term} (HA) is the ability for a service to remain operational and accessible in the presence of unexpected failures. [Disaster recovery](#x2113280){: term} is the process of recovering the service instance to a working state.
{: shortdesc}



{{site.data.keyword.vmware-service_full}} is a highly available regional service designed for availability during a zonal outage. {{site.data.keyword.vmware-service_short}} is designed to meet the [Service Level Objectives (SLO)](/docs/resiliency?topic=resiliency-slo) with the Standard plan.



For more information about the available region and data center locations, see [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).


## High availability architecture
{: #ha-architecture}



### High availability features
{: #ha-features}

{{site.data.keyword.vmware-service_short}} supports the following high availability features:



| Feature | Description | Consideration |
| -------------- | -------------- | -------------- |
| Compute regional HA | Ensures workload uptime through maintaining resources to run workloads across two zones. Workloads migrate to the healthy zone in case of a zonal failure. | Available in the Washington DC region for both networking and compute resources. |
| Network regional HA | Ensure workloads maintain networking durability across zonal failures. | Deploy the HA edge on a stretched resource pool or consolidate your network across two resource pools in a multizone region. |
| Swap locations | Swap primary and secondary network locations for a highly available network edge. | The primary location is the preferred location for your workloads. In case of an outage at the primary location, the secondary location tempoararily becomes the active location.  |
{: caption="HA features for {{site.data.keyword.vmware-service_short}}" caption-side="bottom"}

## Disaster recovery architecture
{: #disaster-recovery-intro}



### Disaster recovery features
{: #dr-features}

{{site.data.keyword.vmware-service_short}} supports the following disaster recovery features:



| Feature | Description | Consideration |
| -------------- | -------------- | -------------- |
| VMware Cloud Director Availability | Replicate workloads from a source {{site.data.keyword.vmware-service_short}} environment over to a second {{site.data.keyword.vmware-service_short}} environment. You can replicate source workloads to any VMware environment including {{site.data.keyword.cloud_notm}}, other Cloud vendors, and on-premesis.  | Included by default in all multitenant virtual data centers (VDCs) and optionally included in your single-tenant Cloud Director site order. |
| Veeam® Backup | Achieve cyber-secure recovery points for your applications and data. | Service charges are incurred only if you choose to include the service in your order. |
{: caption="DR scenarios for {{site.data.keyword.vmware-service_short}}" caption-side="bottom"}

## Your responsibilities for HA and DR
{: #feature-responsibilities}

It is your responsibility to continuously test your plan for HA and DR.

Interruptions in network connectivity and short periods of unavailability of a service might occur. It is your responsibility to make sure that application source code includes [client availability retry logic](/docs/resiliency?topic=resiliency-high-availability-design#client-retry-logic-for-ha) to maintain high availability of the application.
{: note}

For more information about responsibility ownership between you and {{site.data.keyword.cloud_notm}} for {{site.data.keyword.vmware-service_short}}, see [Shared responsibilities for using {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).

For more information about your responsibilities, see [Understanding your responsibilities when using {{site.data.keyword.vmware-service_short}}](/docs/vmware-service?topic=vmware-service-vmaas-understand-responsib).

## Recovery time objective (RTO) and recovery point objective (RPO)
{: #rto-rpo-features}



{{site.data.keyword.cloud_notm}} has [business continuity](#x3026801){: term} plans in place to provide for the recovery of services within hours if a disaster occurs. You are responsible for your data backup and associated recovery of your content.

{{site.data.keyword.vmware-service_short}} provides mechanisms to protect your data and restore service functions. Business continuity plans are in place to achieve targeted [recovery point objective](#x3429911){: term} (RPO) and [recovery time objective](#x3167918){: term} (RTO) for the service. The following table outlines the targets for {{site.data.keyword.vmware-service_short}}.

| Disaster recovery objective | Target value | Method |
|:--------------------------- |:------------ |:------ |
| RPO | 24 h | Use a backup provider such as Veeam Backup and Recovery to store periodic backups of your workload. |
| RPO | Minutes | Use a replication provider such as Veeam to replicate your workload to another location. |
| RTO | Minutes to hours | The recovery time objective depends on the storage medium that is used for your backups and on how long it takes for your workload to be ready from a cold start. |
{: caption="RPO and RTO for {{site.data.keyword.vmware-service_short}}" caption-side="bottom"}

## Change management
{: #change-management}



Change management includes tasks such as upgrades, configuration changes, and deletion.

Grant users and processes the IAM roles and actions with the least privilege that is required for their work. For more information, see [How can I prevent accidental deletion of services?](/docs/resiliency?topic=resiliency-dr-faq#prevent-accidental-deletion).
{: tip}



Consider creating a manual backup before you upgrade to a new version of {{site.data.keyword.vmware-service_short}}.

## How {{site.data.keyword.IBM_notm}} supports disaster recovery planning
{: #ibm-disaster-recovery}

{{site.data.keyword.IBM_notm}} takes specific recovery actions for {{site.data.keyword.vmware-service_short}} if a disaster occurs.

### How {{site.data.keyword.IBM_notm}} recovers from zone failures
{: #ibm-zone-failure}



If a zone failure occurs, {{site.data.keyword.IBM_notm}} resolves the zone outage. When the zone is restored, the global load balancer automatically resumes routing traffic to the restored instance without customer action.

### How {{site.data.keyword.IBM_notm}} recovers from regional failures
{: #ibm-regional-failure}





If regional data remains intact, the service instance is restored to its previous state with the same connection strings. RTO = x, RPO = x minutes."

If regional state is corrupted, the service is restored from the last internal backups that are stored in a cross-region {{site.data.keyword.cloud_notm}} Object Storage bucket. This might result in up to 24 hours of data loss.

If {{site.data.keyword.IBM_notm}} can’t restore the service instance, you must restore the service as described in the [Disaster recovery architecture](#disaster-recovery-intro).

## How {{site.data.keyword.IBM_notm}} maintains services
{: #ibm-service-maintenance}



All upgrades follow {{site.data.keyword.IBM_notm}} service best practices, including recovery plans and rollback processes. Regular maintenance might cause short interruptions, mitigated by [client availability retry logic](/docs/resiliency?topic=resiliency-high-availability-design#client-retry-logic-for-ha). Changes are rolled out sequentially, region by region, and zone by zone within a region. {{site.data.keyword.IBM_notm}} reverts updates at the first sign of a defect.



Complex changes are enabled and disabled with feature flags to control exposure.



Changes that impact customer workloads are detailed in {{site.data.keyword.cloud_notm}} notifications. For more information about planned maintenance, announcements, and release notes that impact this service, see [Monitoring notifications and status](/docs/account?topic=account-viewing-cloud-status).
