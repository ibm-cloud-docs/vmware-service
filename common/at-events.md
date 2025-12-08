---

copyright:
  years: 2024, 2025
lastupdated: "2025-12-08"

keywords: activity tracking, tracking locations, enable events, view events, analyze events

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Activity tracking events for {{site.data.keyword.vcf-aas}}
{: #at_events}

{{site.data.content.vms-deprecated-note}}

{{site.data.keyword.cloud_notm}} services, such as {{site.data.keyword.vmware-service_notm}}, generate activity tracking events.
{: shortdesc}

Activity tracking events report on activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use the events to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. 

You can use {{site.data.keyword.atracker_full_notm}}, a platform service to route auditing events in your account to destinations of your choice by configuring targets and routes that define where activity tracking events are sent. For more information, see [About {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-about).

{{site.data.keyword.vcf-aas-full}} events are global events. For more information, see [Event types](/docs/atracker?topic=atracker-event_types).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

## Locations where activity tracking events are generated
{: #at-locations}

{{site.data.keyword.vcf-aas}} generates activity tracking events in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`) | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|------------------------|--------------------|----------------------|
| [Yes]{: tag-green}  | [Yes]{: tag-green}     | [Yes]{: tag-green} | [Yes]{: tag-green}      |
{: caption="Regions where activity tracking events are generated in Americas locations" caption-side="bottom"}
{: #at-table-1}
{: tab-title="Americas"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)   | Osaka (`jp-osa`) | Chennai (`in-che`) |
|--------------------|------------------|--------------------|
| [Yes]{: tag-green} | [No]{: tag-red}  | [No]{: tag-red}    |
{: caption="Regions where activity tracking events are generated in Asia Pacific locations" caption-side="bottom"}
{: #at-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------|------------------|------------------|
| [Yes]{: tag-green} | [Yes]{: tag-green} | [Yes]{: tag-green} | 
{: caption="Regions where activity tracking events are generated in Europe locations" caption-side="bottom"}
{: #at-table-3}
{: tab-title="Europe"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

## Events that are related to virtual data centers
{: #at-events-vdc}

Events are generated to track how users and applications interact with virtual data centers (VDCs). The following table lists the actions that generate and send events to {{site.data.keyword.at_short}}.

| Action | Description |
|:------ |:----------- |
| `vmware.vdc.create` | An event is generated when a VDC instance is created. |
| `vmware.vdc.delete` | An event is generated when a VDC instance is deleted. |
| `vmware.vdc.update` | An event is generated when a VDC instance is modified. |
| `vmware.sharedsite.create` | An event is generated when the VMware Cloud Director™ site creates a VDC on the multitenant site for the first time. |
| `vmware.sharedsite.delete` | An event is generated when the VMware Cloud Director site deletes a VDC on the multitenant site. |
{: caption="Description of actions that generate events related to VDCs" caption-side="bottom"}

## Events that are related to director site management
{: #at-events-director-site}

Events are generated when you access VMware Cloud Director in {{site.data.keyword.vcf-aas}}. The following table provides the actions that generate and send events to {{site.data.keyword.at_short}}.

| Action | Description |
|:------ |:----------- |
| `vmware.directorsite.create` | An event is generated when a VMware Cloud Director site is created. |
| `vmware.directorsite.delete` | An event is generated when a VMware Cloud Director site is deleted. |
| `vmware.directorsite-pvdc.create` | An event is generated when a VMware Cloud Director site resource pool is created. |
| `vmware.directorsite-pvdc.delete` | An event is generated when a VMware Cloud Director site resource pool is deleted. |
| `vmware.directorsite-cluster.create` | An event is generated when a VMware Cloud Director site cluster is created. |
| `vmware.directorsite-cluster.delete` | An event is generated when a VMware Cloud Director site cluster is deleted. |
| `vmware.directorsite-host.add` | An event is generated when a host is added to a VMware Cloud Director site. |
| `vmware.directorsite-host.remove` | An event is generated when a host is removed from a VMware Cloud Director site. |
| `vmware.directorsite-nfs-storage.add` | An event is generated when NFS storage is added to a VMware Cloud Director site. |
| `vmware.directorsite-nfs-storage.remove` | An event is generated when NFS storage is removed from a VMware Cloud Director site. |
| `vmware.directorsite.password-reset` | An event is generated when the user password for a VMware Cloud Director site is reset. |
| `vmware.directorsite-iam.config` | An event is generated when the OpenID Connect (OIDC) for a VMware Cloud Director site is configured. |
| `vmware.directorsite-iam.read` | An event is generated when the OIDC for a VMware Cloud Director site is checked. Monitoring is not enabled yet. |
{: caption="Description of actions that generate events related to VMware Cloud Director site management" caption-side="bottom"}

## Related links
{: #at-events-links}

* [Getting started with {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-getting-started)
* [Getting started with {{site.data.keyword.logs_full_notm}}](/docs/cloud-logs?topic=cloud-logs-getting-started)
