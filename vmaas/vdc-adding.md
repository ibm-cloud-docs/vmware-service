---

copyright:

  years: 2022, 2023

lastupdated: "2023-04-10"

keywords: add virtual data center, virtual data center, add virtual data center, vdc add

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding virtual data centers
{: #vdc-adding}

With a {{site.data.keyword.vmware-service_full}} single tenant instance, you can control and manage the capacity that is used to run VMware® workloads. You can add virtual data centers (VDCs) to the instance to deploy and run VMware virtualized networking and to run VMware workloads. 

You can deploy one or more VDCs in a {{site.data.keyword.vmware-service_short}} single tenant instance. The minimum instance configuration consists of two hosts (2 Sockets - 32 Cores and 192 GB RAM). You can order up to 100 efficiency edges or one performance edge of medium size until more hosts are added to one of the clusters in the provider virtual data center (PVDC).

## Virtual data center name
{: #vdc-adding-vdc-name}

The VDC name is set to **vdc-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify a VDC name that meets the following requirements:
* The maximum length is 128 characters.
* Only alphanumeric, dash (-), and underscore (_) characters are allowed.
* The name must be unique within all active VDCs in your account. You can create a VDC that has the same name as a previously deleted VDC.

## Procedure to add virtual data centers
{: #vdc-adding-procedure}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vmware-service_short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click an instance name.
3. Click the **Infrastructure** tab. If the instance has multiple PVDCs, ensure that the appropriate PVDC tab is selected.
4. Click the **Data centers** tab and click **Add VDC +**.
5. On the **Virtual data center** page, specify the VDC name, the resource group, and the site and PVDC names. The site and PVDC names are preset based on the instance settings, but you can change them.
6. To order a network edge, ensure that the **Create network edge** checkbox is selected and specify the edge type, either **Efficiency** or **Performance**. Edge storage costs might occur for either edge type.

   | Edge type | Details |
   |:--------- |:------- |
   | Efficiency | These edges allocate networking resources that can be used by up to 100 VDCs before another efficiency edge needs to be created. The first time an efficiency edge is selected new CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. Subsequent VDCs up to 100 can use this edge at no extra cost. This option is suitable for saving resources and costs with independent networking control per VDC. |
   | Performance | These edges allocate new networking resources that are attached to the single VDC. New CPU, RAM, and storage resources are required. CPU and RAM are used from the single tenant site. New edge storage is allocated at a cost. |
   {: caption="Table 1. Network edge descriptions" caption-side="bottom"}

7. For the **Performance** edge type, specify the edge size: 
   * **Medium** - This option is suitable when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput requirement is less than 2 Gbps.
   * **Large** - This option is suitable when only L2 through L4 features such as NAT, routing, L4 firewall, L4 load balancer are required and the total throughput is in the range 2 - 10 Gbps.
   * **Extra Large** - This option is suitable when the total throughput required is multiple Gbps for L7 and VPN.

8. You can also clear the **Create network edge** checkbox to create a VDC without a network edge. This option is suitable for centralized networking administration and control over multiple VDCs.

9. After all configurations are set, review the cost, and click **Create** to submit the VDC order.

## Results after you add virtual data centers
{: #vdc-adding-results}

* The deployment of the resources starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the VDC status.
* When all resources are successfully deployed, the ordered components are installed on your virtual platform.
* When the resources are ready to use, the status of the VDC is changed to **Available**.

## What to do next
{: #vdc-adding-next}

1. [View the virtual data center](/docs/vmware-service?topic=vmware-service-vdc-view-delete#vdc-view-delete-details) that you ordered.
2. [Set the admin password](/docs/vmware-service?topic=vmware-service-accessing-vcd-console#accessing-vcd-console-reset-proc) for the VMware Cloud Director console.

## Related links
{: #vdc-adding-links}

* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
* [Visualizing your site with {{site.data.keyword.cloud}} Monitoring](/docs/vmware-service?topic=vmware-service-single-tenant-monitoring)
