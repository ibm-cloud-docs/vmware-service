---

copyright:

  years: 2022, 2024

lastupdated: "2024-01-22"

keywords: monitoring, sysdig, vmware multitenant monitor, vmware single tenant monitor, vmware site management monitoring, view metrics

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Visualizing your site with {{site.data.keyword.mon_full_notm}}
{: #single-tenant-monitoring}

{{site.data.keyword.at_full}} provides an integration with {{site.data.keyword.mon_full}}, which allows you to use a VMware® site provided default dashboard to view metrics for your sites. Alternatively, you can create your own dashboard to visualize performance, volume of usage, and to define alerts to monitor your environment.

Use {{site.data.keyword.mon_short}} dashboards to complete the following tasks.

* Explore and easily visualize your environment.
* Accelerate a diagnosis and a resolution for performance incidents.
* Control cost of monitoring infrastructure.
* Mitigate impact of abnormal situations with proactive notifications.

For more information about the benefits of using {{site.data.keyword.mon_short}}, see [Getting started with {{site.data.keyword.mon_full_notm}}](/docs/monitoring?topic=monitoring-getting-started).

## Monitoring VMware sites
{: #single-tenant-monitoring-sites}

Consider the following tasks, predefined alerts, and what they mean when you monitor an instance of the VMware multitenant or single-tenant service:

| Task | Predefined alert | What to look for |
|:---- |----------------- |----------------- |
| Monitor CPU usage per cluster to prevent CPU resource exhaustion. The default is to alert after CPU usage is over 80% for any cluster in the site | [VMware Site] Cluster CPU Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with more bare metal servers. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
| Monitor memory usage per cluster to prevent memory resource exhaustion. The default is to alert after memory usage is over 80% for any cluster in the site.| [VMware Site] Cluster Memory Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with more bare metal servers. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
| Monitor storage usage per cluster to prevent storage resource exhaustion. The default is to alert after storage usage is over 80% for any cluster in the site | [VMware Site] Cluster Storage Usage | Frequent triggering of this alert might be an indication that you need to scale up your cluster with storage. Each of the four performance tiers for the storage that is used in the cluster can be monitored and can receive alerts independently. As usage reaches 100%, VMware workloads start to fail, and new deployments of workloads fail. |
{: caption="Table 1. Tasks and predefined alerts" caption-side="bottom"}

## {{site.data.keyword.vmware-service_short}} predefined dashboard
{: #single-tenant-monitoring-dashboards}

Use predefined dashboards to monitor {{site.data.keyword.vmware-service_short}} metrics. The following dashboards are the default dashboard when you start the Sysdig web UI from your service instance UI.

The default dashboard cannot be changed, but you can copy the dashboard to update it to suit your needs.
{: important}

### Single-tenant dashboards
{: #single-tenant-monitoring-dashboards-st}

Use the `VMware Single-Tenant Site` dashboard to monitor {{site.data.keyword.vmware-service_short}} single-tenant metrics.

### Multitenant dashboards
{: #single-tenant-monitoring-dashboards-mt}

Use the `VMware as a Service - Director Site` and `VMware as a Service - Virtual Data Center` dashboards to monitor {{site.data.keyword.vmware-service_short}} multitenant metrics.

## Single-tenant metrics
{: #single-tenant-monitoring-metrics}

The following metrics are available for the VMware single-tenant site.

### Site cluster name
{: #single-tenant-monitoring-metrics-name}

The following table displays the name of the single-tenant site cluster.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster` |
{: caption="Table 2. Cluster name metadata" caption-side="bottom"}

### Site cluster ID
{: #single-tenant-monitoring-metrics-id}

The following table displays the ID of the single-tenant site cluster.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_id` |
{: caption="Table 3. Cluster ID metadata" caption-side="bottom"}

### Site cluster CPU usage
{: #single-tenant-monitoring-metrics-cpu}

The following table displays the total usage for the VMware single-tenant site cluster CPU.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_cpu_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 4. CPU usage metadata" caption-side="bottom"}

### Site cluster memory usage
{: #single-tenant-monitoring-metrics-memory}

The following table displays the total usage for the VMware single-tenant site cluster memory.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_memory_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 5. Memory usage metadata" caption-side="bottom"}

### Site cluster 0.25 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-storage-25}

The following table displays the total usage for the VMware single-tenant cluster storage for 0.25 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_point_two_five_iopsgb_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit`  | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 6. 0.25 IOPS/GB storage usage metadata" caption-side="bottom"}

### Site cluster 2 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-2}

The following table displays the total usage for the VMware single-tenant cluster storage for 2 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_two_iopsgb_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 7. 2 IOPS/GB storage usage metadata" caption-side="bottom"}

### Site cluster 4 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-4}

The following table displays the total usage for the VMware single-tenant cluster storage for 4 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_four_iopsgb_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 8. 4 IOPS/GB storage usage metadata" caption-side="bottom"}

### Site cluster 10 IOPS/GB storage usage
{: #single-tenant-monitoring-metrics-10}

The following table displays the total usage for the VMware single-tenant cluster storage for 10 IOPS/GB.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_ten_iopsgb_usage_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 9. 10 IOPS/GB storage usage metadata" caption-side="bottom"}

### Site cluster vSAN storage usage
{: #single-tenant-monitoring-metrics-vsan}

The following table displays the percentage of usable capacity for the VMware single-tenant cluster vSAN storage.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_vsan_percent` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 10. vSAN storage usage metadata" caption-side="bottom"}

### Site cluster vSAN storage raw disk space usage
{: #single-tenant-monitoring-metrics-vsan-raw}

The following table displays the total raw disk space for the VMware single-tenant cluster vSAN storage.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_vsan_total_raw_disk_space` |
| `Metric Type` | `gauge` |
| `Unit` | `GB` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 11. vSAN storage raw disk space usage metadata" caption-side="bottom"}

### Site cluster vSAN storage disk space usage
{: #single-tenant-monitoring-metrics-vsan-use}

The following table displays the total used disk space for the VMware single-tenant cluster vSAN storage.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_directorsite_cluster_storage_vsan_used_disk_space` |
| `Metric Type` | `gauge` |
| `Unit` | `GB` |
| `Segment By` | `VMware Single Tenant Site cluster name` |
{: caption="Table 12. vSAN storage raw disk space usage metadata" caption-side="bottom"}

## Multitenant metrics
{: #single-tenant-monitoring-metrics-mt}

The following metrics are available for the VMware multitenant site.

### Virtual data center memory allocation
{: #single-tenant-monitoring-metrics-mt-memory-allocation}

The following table displays the total allocation of the VMware virtual data center memory.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_memory_allocation` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 13. VDC memory allocation" caption-side="bottom"}

### Virtual data center memory usage
{: #single-tenant-monitoring-metrics-mt-memory-usage}

The following table displays the total usage of the VMware virtual data center memory.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_memory_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 14. VDC memory usage" caption-side="bottom"}

### Virtual data center storage usage
{: #single-tenant-monitoring-metrics-mt-storage-usage}

The following table displays the total usage of the VMware virtual data center storage.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 15. VDC storage usage" caption-side="bottom"}

### Virtual data center vCPU allocation
{: #single-tenant-monitoring-metrics-mt-vcpu-allocation}

The following table displays the total allocation of the VMware virtual data center vCPU.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_vcpu_allocation` |
| `Metric Type` | `gauge` |
| `Unit` | `none` |
| `Segment By` | `Service instance name` |
{: caption="Table 16. VDC vCPU allocation" caption-side="bottom"}

### Virtual data center vCPU usage
{: #single-tenant-monitoring-metrics-mt-vcpu-usage}

The following table displays the total usage of the VMware virtual data center vCPU.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_vcpu_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `none` |
| `Segment By` | `Service instance name` |
{: caption="Table 17. VDC vCPU usage" caption-side="bottom"}

### Virtual data center disk usage for 0.25 IOPS/GB
{: #single-tenant-monitoring-metrics-mt-25-iops}

The following table displays the total disk space usage of the VMware virtual data center storage at the 0.25 IOPS/GB tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_point_two_five_iopsgb_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 18. VDC 0.25 IOPS/GB storage" caption-side="bottom"}

### Virtual data center disk usage for 2 IOPS/GB
{: #single-tenant-monitoring-metrics-mt-two-iops}

The following table displays the total disk space usage of the VMware virtual data center storage at the 2 IOPS/GB tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_two_iopsgb_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 19. VDC 2 IOPS/GB storage" caption-side="bottom"}

### Virtual data center disk usage for 4 IOPS/GB
{: #single-tenant-monitoring-metrics-mt-four-iops}

The following table displays the total disk space usage of the VMware virtual data center storage at the 4 IOPS/GB tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_four_iopsgb_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 20. VDC 4 IOPS/GB storage" caption-side="bottom"}

### Virtual data center disk usage for 10 IOPS/GB
{: #single-tenant-monitoring-metrics-mt-ten-iops}

The following table displays the total disk space usage of the VMware virtual data center storage at the 10 IOPS/GB tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_ten_iopsgb_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 21. VDC 10 IOPS/GB storage" caption-side="bottom"}

### Virtual data center disk usage for standard IOPS/GB
{: #single-tenant-monitoring-metrics-mt-standard-iops}

The following table displays the total disk space percent of the VMware virtual data center storage at the standard IOPS/GB tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_standard_iopsgb_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `percent` |
| `Segment By` | `Service instance name` |
{: caption="Table 22. VDC standard IOPS/GB storage" caption-side="bottom"}

### Virtual data center storage usage for vSAN
{: #single-tenant-monitoring-metrics-mt-vsan}

The following table displays the total disk space usage of the VMware virtual data center storage at the vSAN tier.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_storage_vsan_usage` |
| `Metric Type` | `gauge` |
| `Unit` | `byte` |
| `Segment By` | `Service instance name` |
{: caption="Table 23. VDC vSAN storage" caption-side="bottom"}

### Virtual data center storage name
{: #single-tenant-monitoring-metrics-mt-storage-name}

The following table displays the name of the VMware virtual data center storage.

| Metadata | Description |
|:-------- |:----------- |
| `Metric Name` | `ibm_vmware_vdc_datastore` |
{: caption="Table 24. VDC storage name" caption-side="bottom"}
