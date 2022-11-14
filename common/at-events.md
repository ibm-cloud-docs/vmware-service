---

copyright:

  years: 2022

lastupdated: "2022-11-07"

keywords: activity tracker, event, vmware virtual data center events, vmware site management events, view events

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Auditing events for {{site.data.keyword.vmware-service_short}}
{: #at-events}

Use the {{site.data.keyword.at_full}} service to track how users and applications interact with {{site.data.keyword.cloud}} for VMware® in the {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.at_full_notm}} records user-initiated activities that change the state of a service in the {{site.data.keyword.cloud_notm}}. You can use this service to investigate for abnormal activity and critical actions, and comply with regulatory audit requirements. In addition, you can be alerted on actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, see [Getting started with {{site.data.keyword.at_short}}](/docs/activity-tracker?topic=activity-tracker-getting-started).

## Events that are related to virtual data centers
{: #at-events-vdc}

Events are generated to track how users and applications interact with virtual data centers. The following table lists the actions that generate and send events to {{site.data.keyword.at_short}}.

| Action | Description |
|:------ |:----------- |
| `vmware.vdc.create` | An event is generated when a virtual data center instance is created. |
| `vmware.vdc.delete` | An event is generated when a virtual data center instance is deleted. |
{: caption="Table 1. Description of actions that generate events related to virtual data centers" caption-side="bottom"}

## Events that are related to director site management
{: #at-events-director-site}

Events are generated when you access VMware Cloud Director in {{site.data.keyword.cloud}} for VMware. The following table provides the actions that generate and send events to {{site.data.keyword.at_short}}.

| Action | Description |
|:------ |:----------- |
| `vmware.directorsite.create` | An event is generated when a vCloud Director site is created. |
| `vmware.directorsite.delete` | An event is generated when a vCloud Director site is deleted. |
| `vmware.directorsite-host.add` | An event is generated when a host is added to a vCloud Director site. |
| `vmware.directorsite-host.remove` | An event is generated when a host is removed from a vCloud Director site. |
| `vmware.directorsite-nfs-storage.add` | An event is generated when NFS storage is added to a vCloud Director site. |
| `vmware.directorsite-nfs-storage.remove` | An event is generated when NFS storage is removed from a vCloud Director site. |
| `vmware.directorsite.password-reset` | An event is generated when the user password for a vCloud Director site is reset. |
{: caption="Table 2. Description of actions that generate events related to vCloud Director site management" caption-side="bottom"}

## Viewing events
{: #at-events-viewing}

{{site.data.keyword.cloud_notm}} for VMware events are global events. For more information, see [Monitoring global and location-based events](/docs/activity-tracker?topic=activity-tracker-monitor_events#mon_def_event_type).

{{site.data.keyword.at_full_notm}} can have only one instance per location. To view events, you must access the web UI of the {{site.data.keyword.at_full_notm}} service in the same location where your service instance is available. For more information, see [Navigating to the UI](/docs/activity-tracker?topic=activity-tracker-launch#launch).
