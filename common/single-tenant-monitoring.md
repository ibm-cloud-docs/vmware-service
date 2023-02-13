---

copyright:

  years: 2022, 2023

lastupdated: "2023-01-26"

keywords: monitoring, sysdig, vmware single tenant monitor, vmware site management monitoring, view metrics

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Visualizing your site with IBM Cloud Monitoring
{: #single-tenant-monitoring}

{{site.data.keyword.at_full}} provides an integration with {{site.data.keyword.mon_short}}, which allows you to use a VMware® site provided default dashboard to view metrics for your sites. Alternatively, you can create your own dashboard to visualize performance, volume of usage, and to define alerts to monitor your environment.

Use {{site.data.keyword.mon_short}} dashboards to complete the following tasks.

* Explore and easily visualize your environment.
* Accelerate a diagnosis and a resolution for performance incidents.
* Control cost of monitoring infrastructure.
* Mitigate impact of abnormal situations with proactive notifications.

For more information about the benefits of using {{site.data.keyword.mon_short}}, see [Getting started with {{site.data.keyword.cloud_notm}} Monitoring](/docs/monitoring?topic=monitoring-getting-started#getting-started-features).

## Monitoring VMware sites
{: #single-tenant-monitoring-sites}

Consider the following tasks, predefined alerts, and what they mean when you monitor an instance of the VMware single-tenant service:

| Task | Predefined alert | What to look for |
|:---- |----------------- |----------------- |
| Monitor CPU usage per cluster to prevent CPU resource exhaustion. The default is to alert after CPU usage is over 80% for any cluster in the site | [VMware Site] Cluster CPU Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with more bare metal servers. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
| Monitor memory usage per cluster to prevent memory resource exhaustion. The default is to alert after memory usage is over 80% for any cluster in the site.| [VMware Site] Cluster Memory Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with more bare metal servers. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
| Monitor storage usage per cluster to prevent storage resource exhaustion. The default is to alert after storage usage is over 80% for any cluster in the site | [VMware Site] Cluster Storage Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with storage. Each of the four performance tiers for the storage that is used in the cluster can be monitored and can receive alerts independently. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
{: caption="Table 1: Tasks and predefined alerts" caption-side="top"}

## {{site.data.keyword.vmware-service_short}} predefined dashboard
{: #single-tenant-monitoring-dashboards}

The predefined dashboard that you can use to monitor {{site.data.keyword.vmware-service_short}} metrics is called `VMware Single-Tenant Site` and it's the default dashboard when you start the Sysdig web UI from your service instance UI.

The VMware single-tenant site provides the following metrics for the default dashboard:

* Cluster CPU usage percent
* Cluster memory usage percent
* Cluster storage usage at the 0.25 IOPS/GB storage tier
* Cluster storage usage at the 2 IOPS/GB storage tier
* Cluster storage usage at the 4 IOPS/GB storage tier
* Cluster storage usage at the 10 IOPS/GB storage tier

The default dashboard cannot be changed, but you can copy the dashboard to update it to suit your needs.
{: important}

## Metrics
{: #single-tenant-monitoring-metrics}

The following metrics are available for the VMware single-tenant site.

### Cluster CPU usage
{: #single-tenant-monitoring-metrics-cpu}

The following table displays the total usage for the VMware single-tenant site cluster CPU.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_cpu_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type` | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 2: CPU usage metadata" caption-side="top"}

### Cluster memory usage
{: #single-tenant-monitoring-metrics-memory}

The following table displays the total usage for the VMware single-tenant site cluster memory.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_memory_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type` | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 3: Memory usage metadata" caption-side="top"}

### Cluster 0.25 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-storage-25}

The following table displays the total usage for the VMware single-tenant cluster storage for 0.25 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_point_two_five_iopsgb_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type`  | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 4: 0.25 IOPS/GB storage usage metadata" caption-side="top"}

### Cluster 2 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-2}

The following table displays the total usage for the VMware single-tenant cluster storage for 2 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_two_iopsgb_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type` | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 5: 2 IOPS/GB storage usage metadata" caption-side="top"}

### Cluster 4 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-4}

The following table displays the total usage for the VMware single-tenant cluster storage for 4 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_four_iopsgb_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type` | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 6: 4 IOPS/GB storage usage metadata" caption-side="top"}

### Cluster 10 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-10}

The following table displays the total usage for the VMware single-tenant cluster storage for 10 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_ten_iopsgb_usage_percent`|
| `Metric Type` | `gauge` |
| `Value Type` | `percent` |
| `Segment By` | `Service instance, VMware Site cluster, Service instance name` |
{: caption="Table 7: 10 IOPS/GB storage usage metadata" caption-side="top"}
