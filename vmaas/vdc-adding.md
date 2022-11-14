---

copyright:

  years: 2022

lastupdated: "2022-11-09"

keywords: add virtual data center, virtual data center, add virtual data center, vdc add

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding virtual data centers
{: #vdc-adding}

The instance is not directly used to run VMware workloads. VMware virtual data centers (VDCs) are used to deploy and run VMware virtualized networking and run VMware workloads. 

You can deploy one or more VDCs in an instance except when you are using the minimum instance configuration. The minimum configuration consists of 2 hosts (2 Sockets - 32 Cores, 192 GB RAM). You can start with just 1 VDC and a performance network edge of medium size until more hosts are added to the cluster.

## Minimum requirements for {{site.data.keyword.vmware-service_short}} instances
{: #vdc-adding-min-req}

The minimum initial order and cluster size is:
   * 2 hosts (2 Sockets - 32 Cores, 192 GB RAM)
   * 24 TB of shared storage

You can start with just one virtual data center (VDC) and a performance network edge of medium size.

## Virtual data center name
{: #vdc-adding-vdc-name}

The VDC name is set to **vdc-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify a VDC name that meets the following requirements:
* The maximum length is 128 characters.
* Only alphanumeric, dash (-), and underscore (_) characters are allowed.
* The name must be unique within all active VDCs in your account. You can create a VDC that has the same name as a previously deleted VDC.

## Procedure to order virtual data centers
{: #vdc-adding-procedure}

1. In the {{site.data.keyword.vmware-service_short}} console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
3. Click the **Infrastructure** tab.
4. In the **Virtual data centers (VDCs)** section, click **Add new**.
5. On the **Virtual data center** page, specify the resource name and group, and the site and cluster names. These site and cluster name are preset based on the instance settings, but you can change them.
6. Specify the network edge type, either **Efficiency** or **Performance**. Edge storage costs might occur for either option.

   | Edge type | Details |
   |:--------- |:------- |
   | Efficiency | These edges allocate networking resources that can be used by up to 100 VDCs before another efficiency edge needs to be created. The first time an efficiency edge is selected new CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. Subsequent VDCs up to 100 can use this edge at no extra cost. |
   | Performance | These edges allocate new networking resources that are attached to the single VDC. New CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. |
   {: caption="Table 1. Network edge descriptions" caption-side="bottom"}

7. After all configurations are set, review the cost, and click **Create** to submit the VDC order.

## Results after you add virtual data centers
{: #vdc-adding-results}

* The deployment of the resources starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the VDC status.
* When all resources are successfully deployed, the ordered components are installed on your virtual platform.
* When the resources are ready to use, the status is changed to **Ready to use**.

## What to do next
{: #vdc-adding-next}

1. [View the virtual data center](/docs/vmware-service?topic=vmware-service-vdc-view-delete#vdc-view-delete-details) that you ordered.
2. [Set the admin password](/docs/vmware-service?topic=vmware-service-accessing-vcd-console#accessing-vcd-console-reset-proc) for the VMware Cloud Director Management console.

## Related links
{: #vdc-adding-links}

* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
