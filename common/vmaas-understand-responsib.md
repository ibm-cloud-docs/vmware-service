---

copyright:
  years: 2022, 2025

lastupdated: "2025-07-08"

subcollection: vmware-service

keywords: ibm responsibilities, customer responsibilities, management responsibilities

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when you use {{site.data.keyword.vcf-aas}}
{: #vmaas-understand-responsib}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.vmware-service_full}}. For a high-level view of the service types in {{site.data.keyword.cloud_notm}} and the breakdown of responsibilities between the customer and {{site.data.keyword.IBM}} for each type, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).
{: shortdesc}

Review the following sections for the specific responsibilities for you and for {{site.data.keyword.IBM_notm}} when you use {{site.data.keyword.vcf-aas-full}}. For the overall terms of use, see [{{site.data.keyword.cloud_notm}} terms of use](/docs/overview?topic=overview-terms).

## Incident and operations management
{: #vmaas-understand-responsib-incident-and-ops}

Incident and operations management includes tasks such as event management, high availability, problem determination, recovery, and full state backup and recovery.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| High availability | Actively monitor and resolve infrastructure and hypervisor issues. VMware® by Broadcom environments are configured with one spare redundant host for workload availability. | Plan and provision VMware® by Broadcom workloads with HA configurations such as active-passive and active-active. Active-active and active-passive workload deployments are enabled through customer configurations. These deployments consist of multiple instances of the application that are load-balanced based on factors such as application, instance availability, or application instance response performance. |
| Infrastructure health monitoring and notification | Remediate all infrastructure and hypervisor environment issues. Notify customers of applicable incidents. | Ascertain the impact of each incident that is reported. Engage IBM Support as required. |
| Infrastructure health management | Continuously deliver new features, updates, and bug fixes as needed in a manner transparent to you. Schedule maintenance activities that have customer impact in advance and post notifications to the {{site.data.keyword.cloud_notm}} status page. | Set preferences to receive emails notifications. Monitor the {{site.data.keyword.cloud_notm}} status page for general announcements.|
| Clusters, hosts, and storage resource management and observability | Deploy a fully managed single-tenant VMware by Broadcom environment in a secured, IBM-owned infrastructure account to customer specifications. Fulfill customer requests for more infrastructure, such as adding and removing single-tenant clusters, bare metal compute, and storage. Integrate ordered infrastructure resources to work automatically with your cluster architecture and become available to your deployed apps and workloads. Provide monitoring by using IBM Cloud Monitoring to enable observability of your clusters. | Control the amount of deployed infrastructure and ensure that the VMware by Broadcom environment has the proper amount of storage, networking, and compute resources to run workloads. Monitor compute, RAM, and storage usage in [Cloud Monitoring](https://cloud.ibm.com/observability/catalog/ibm-cloud-monitoring). Use the provided console tools to adjust {{site.data.keyword.vcf-aas}} instance compute and storage capacity to meet the needs of your workload. |
| Application networking | Deploy fully managed single-tenant VMware NSX-T™ edge configurations that are attached to virtual data centers that can be used to access the public internet and {{site.data.keyword.cloud_notm}} private internet. | Use the provided console tools to configure multiple virtual data centers to a single edge configuration. Or select a one-to-one virtual data center to networking edge mapping based on use case and bandwidth. When you put VMware by Broadcom workloads on the public and private {{site.data.keyword.cloud_notm}} network, use NSX-T edge services firewalls, OS or application firewalls, and OS or application security configurations to protect workloads from threats and attacks. |
| Workload monitoring | Forward to customer any network intrusion notifications detected. Triage virtualization and backup-related errors to determine whether the customer issue needs assistance. Remediate all hardware failures, notification of potential workload impact. | Monitor and respond to OS or software failures, backup, and replication jobs. Engage IBM Support as required. |
| Full state backup and recovery | Back up all management component configurations that support customer instances. | Regularly back up workload deployments and establish the ability to re-create workload deployments. |
| Incident management | Communicate unplanned incidents with customer impact through the CIE process. | If you are an impacted customer, obtain a report about the incident upon request. |
{: row-headers}
{: caption="Responsibilities for incident and operations" caption-side="bottom"}

## Change management
{: #vmaas-understand-responsib-change-management}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Updates, fixes, and new features | Provide regular updates, bug fixes, and new features, following a continuous delivery model in a way that is transparent to you for all infrastructure tools, VMware by Broadcom components, IBM deployed cloud services and IBM management, monitoring, and automation tools. Post notifications for changes that impact you. | Set preferences to receive email notifications. Monitor the {{site.data.keyword.cloud_notm}} status page for general announcements. Use best practices and keep application operating systems and workload applications patched and secure with the most recent security patches. |
{: row-headers}
{: caption="Responsibilities for change management" caption-side="bottom"}

## Identity and access management
{: #vmaas-understand-responsib-iam}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Identity and access | Provide the function to restrict access to resources through the {{site.data.keyword.cloud_notm}} console. Provide default access to the provisioned VMware by Broadcom environment. | Manage access to resources through IAM (Identity and Access Management). Manage access to the VMware by Broadcom environment. |
| Observability | Allow integration of {{site.data.keyword.atracker_full_notm}} with your VMware environment to audit the actions that users take in the cluster. | Set up [{{site.data.keyword.atracker_full_notm}}](/docs/vmware-service?topic=vmware-service-at_events) or other functions to track user activity. |
{: row-headers}
{: caption="Responsibilities for identity and access management" caption-side="bottom"}

## Security and regulation compliance
{: #vmaas-understand-responsib-security-compliance}

Security and regulation compliance includes tasks such as security controls implementation and compliance certification.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Workload compliance | Provide an up-to-date catalog of operating system images. | Configure, harden, maintain, and monitor your virtual machines according to your compliance needs. |
| Encryption | Provide secure SSL connections to administration portals and replication endpoints. Workload can be deployed by using AES 256-bit encrypted data stores with unique key per customer instance. Backups are encrypted uniquely per customer. | Choose encrypted data stores when you are deploying workloads into the environment where appropriate. Use encrypted networking for workload to workload and workload to IBM Cloud Service connections. Use the {{site.data.keyword.cloud_notm}} private network where appropriate. |
{: row-headers}
{: caption="Responsibilities for security and regulation compliance" caption-side="bottom"}

## Disaster recovery
{: #vmaas-understand-responsib-disaster-recovery}

Disaster recovery includes tasks such as providing dependencies on disaster recovery sites, provisioning disaster recovery environments, data and configuration backup, replicating data and configuration to the disaster recovery environment, and failover on disaster events.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Backup of management configuration data | Conduct backups of the management component configurations. These backups include single-tenant vCenter Server, VMware NSX-T, VMware Cloud Director™, and service configurations. Offsite immutable backup copies are enabled in an independent backup account and they run daily. |  |
| Backup of workloads | Enable backup services for customer workload. | Choose and implement a backup provider for critical workloads. For more information, see [Understanding high availability and disaster recovery for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-ha-dr). |
| Recovery of configuration | Conduct recovery in the original data center after the infrastructure is available. |  |
| Recovery of workloads | Restore capabilities are available in normal operations. For configuration restores, provide customer restore services after the infrastructure is available. If an offsite recovery is required, IBM works with the customer to help recover. | Restore backups from your chosen backup provider. For more information, see [Understanding high availability and disaster recovery for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-ha-dr). |
{: row-headers}
{: caption="Responsibilities for disaster recovery" caption-side="bottom"}

## Operating system licensing
{: #vmaas-understand-responsib-os-mgmt}

Operating system (OS) licensing refers to the operating system software and configuration that are deployed in virtual machines or underlying bare metal servers.

| Item | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Workload OS licensing | Provide OS licensing for infrastructure tools part of the service, such as VMware by Broadcom and add-on services solution components. | For single-tenant instances, you must bring your own OS license for your workloads that are running inside your virtual data centers' VMs or vApps. For multitenant instances, bring your own license is not supported and you must purchase {{site.data.keyword.IBM_notm}} licenses. |
{: row-headers}
{: caption="Responsibilities for OS licensing" caption-side="bottom"}
