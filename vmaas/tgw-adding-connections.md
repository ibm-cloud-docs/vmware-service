---

copyright:

  years: 2024, 2025

lastupdated: "2025-05-28"

keywords: add connection, interconnectivity, transit gateway

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Using Transit Gateway to interconnect {{site.data.keyword.vcf-aas}} with IBM Cloud services
{: #tgw-adding-connections}

Use {{site.data.keyword.tg_full}} to securely interconnect {{site.data.keyword.vmware-service_notm}} multitenant and single-tenant virtual data centers (VDCs) to a transit gateway to enable network connectivity into your {{site.data.keyword.cloud_notm}} Classic and Virtual Private Cloud (VPC) IaaS infrastructures, and your on-premises locations by using Direct Link connections. Use the VDC **Interconnectivity** tab in the VMware Solutions console to connect to {{site.data.keyword.tg_short}}.

{{site.data.keyword.tg_short}} uses Generic Routing Encapsulation (GRE) tunnels to connect your single-tenant and multitenant virtual data centers (VDCs) to a {{site.data.keyword.tg_short}} resource. Use the VMware Solutions console to add a connection group to your VDC. A connection group contains six unbound GRE tunnels to establish redundant connectivity to each zone. After you create the connection group, add each GRE tunnel to the {{site.data.keyword.tg_short}} to attach the connection group. You can connect the tunnels to {{site.data.keyword.tg_short}} by using either the {{site.data.keyword.cloud-shell_notm}} or the {{site.data.keyword.tg_short}} console.

You must individually attach all six unbound GRE tunnels to the {{site.data.keyword.tg_short}} to attach the VDC connection group to {{site.data.keyword.tg_short}}. The six unbound GRE tunnels help to avoid redundancy risks.

The {{site.data.keyword.tg_short}} resource does not need to be in the same {{site.data.keyword.cloud_notm}} account as the VDC. The {{site.data.keyword.tg_short}} resource is included in your {{site.data.keyword.cloud_notm}} account, not your VMware® by Broadcom account.

## Before you begin
{: #tgw-adding-connections-prereq}

### Network edge version requirement
{: #tgw-adding-connections-prereq-version}

Your VDC must include a network edge version 2.0 or higher to use {{site.data.keyword.tg_short}}. All VDCs created after 12 January 2024 are a network edge version 2.0 or higher. If your network edge version is not compatible, a notification displays in the VDC **Interconnectivity** tab in the VMware Solutions console.

If your VDC does not include a compatible version, create a new VDC that includes the network edge. For more information, see [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding).

### {{site.data.keyword.tg_short}} requirement
{: #tgw-adding-connections-prereq-version-tgw}

Before you can add a connection group to your VDC, you must create a {{site.data.keyword.tg_short}}. For more information, see the [{{site.data.keyword.tg_short}} console](https://cloud.ibm.com/interconnectivity/transit/provision) and [Getting started with {{site.data.keyword.tg_full_notm}}](/docs/transit-gateway?topic=transit-gateway-getting-started).

## Procedure to connect {{site.data.keyword.vcf-aas}}
{: #tgw-adding-connections-proc}

1. Add a connection group to your VDC.
   1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
   2. On the **{{site.data.keyword.vmware-service_short}}** page, click the virtual data center name.
   3. Click the **Interconnectivity** tab to open the {{site.data.keyword.tg_short}} connections page.
   4. Click **Add connection group +**.
   5. In the **Add connection group** pane, complete the following steps.
      1. Enter the {{site.data.keyword.tg_short}} ID that you want to connect to. You can locate the {{site.data.keyword.tg_short}} ID in the {{site.data.keyword.tg_short}} details page in the [{{site.data.keyword.tg_short}} console](https://cloud.ibm.com/interconnectivity/transit/provision).
      2. Select the region where you want the {{site.data.keyword.tg_short}} to connect.
      3. Click **Add**.

      The connection group with six pending GRE tunnels is added to your VDC and automation runs to generate the connection values. Next, you must individually connect the six unbound GRE tunnels to complete the connection.

      The *Generating connection values* status displays while automation generates the connection values. Refresh the VDC page to confirm that the values are generated before you complete the next step to create the {{site.data.keyword.tg_short}} connection.
      {: note}

2. Connect the connection group unbound GRE tunnels to {{site.data.keyword.tg_short}}.

   Use either the CLI or the {{site.data.keyword.tg_short}} console to connect the tunnels to {{site.data.keyword.tg_short}}. It is recommended to use {{site.data.keyword.cloud-shell_notm}} to create the connection to {{site.data.keyword.tg_short}}.
   {: note}

   * Complete the following steps if you use {{site.data.keyword.cloud-shell_short}} to connect the tunnels to {{site.data.keyword.tg_short}}.
   1. Click the overflow menu in the row of the connection group and click **Generate CLI commands**. A single command for all six GRE tunnels is generated.
   2. In the **Generate CLI commands** pane, click the **Copy to clipboard** icon to copy the single CLI command to connect all six GRE tunnels.
   3. In the {{site.data.keyword.cloud_notm}} console, click the [{{site.data.keyword.cloud-shell_notm}}](https://cloud.ibm.com/shell) icon to open the {{site.data.keyword.cloud-shell_short}} interface.
   4. Paste the CLI command in {{site.data.keyword.cloud-shell_short}} and run the command to connect all six tunnels to {{site.data.keyword.tg_short}}.

   To run the CLI command locally, use the {{site.data.keyword.tg_short}} CLI, which is implemented as an {{site.data.keyword.cloud_notm}} CLI plug-in. For more information, see [Creating an unbound Generic Routing Encapsulation tunnel connection](/docs/transit-gateway?topic=transit-gateway-unbound-gre-connection&interface=cli) and [{{site.data.keyword.tg_short}} CLI change log](/docs/transit-gateway?topic=transit-gateway-cli-change-log&interface=cli).
   {: note}

   * Complete the following steps if you use the {{site.data.keyword.tg_short}} console to connect the tunnels to {{site.data.keyword.tg_short}}.
   1. On the {{site.data.keyword.tg_short}} connections page, expand the {{site.data.keyword.tg_short}} ID. The six pending GRE tunnels display.
   2. Expand an unbound GRE tunnel. The tunnel parameters display. Use the **Copy to clipboard** icon to copy the parameters as you complete the next steps to create the tunnel connection.
   3. Click **Add connection to {{site.data.keyword.tg_short}}** to open the {{site.data.keyword.tg_short}} console.
   4. In the {{site.data.keyword.tg_short}} console, complete the procedure to [create the unbound GRE tunnel connection](/docs/transit-gateway?topic=transit-gateway-unbound-gre-connection&interface=ui). Specify the following parameters.

      * Select **Unbound GRE Tunnel** for the network connection type.
      * Select **Classic Infrastructure** for the base network type.
      * Select **Request connection to a network in another account** for the connection reach. You can copy the **Cloud account ID** from the {{site.data.keyword.tg_short}} connections section on the **Interconnectivity** tab in the VMware Solutions console.
      * Enter the GRE Tunnel connection values that you can copy and paste from the VMware Solutions console.

   The {{site.data.keyword.tg_short}} documentation states that the **Remote BGP ASN** field is optional. However, you must provide the **Remote BGP ASN** value that is specified in the GRE tunnel connection values available to copy in the **Interconnectivity** tab for the VDC.
   {: important}

   5. Repeat the steps to create the unbound GRE tunnel for each unbound GRE tunnel associated with the {{site.data.keyword.tg_short}} ID.

   When all unbound GRE tunnels display the **Attached** status, the connection group is attached to {{site.data.keyword.tg_short}}.

3. Complete the following procedures to configure the VDC network edge.
   1. Add your VDC networks as routed networks. New networks are advertised by default, and you can optionally disable the route advertisement setting for each network separately.
   2. If you have existing SNAT rules, edit the priority and configurations rules and add No Source NAT (NOSNAT) rules to use {{site.data.keyword.tg_short}}. For more information, see [Add an SNAT or a DNAT Rule](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director/vmware-cloud-director/10-5/add-an-snat-or-a-dnat-rule.html).{: external}
   3. Update your firewall rules to allow for the new outbound network traffic and for the new remote network inbound traffic. For more information, see [Configure Firewall Rules on a Provider Gateway in the VMware Cloud Director Tenant Portal](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director/vmware-cloud-director/10-5/map-for-vmware-cloud-director-tenant-portal-guide-10-5/working-with-networks-tenant/working-with-provider-gateways-tenant/configure-firewall-rules-on-a-provider-gateway-tenant.html).{: external}

4.  From [{{site.data.keyword.tg_short}}](https://cloud.ibm.com/interconnectivity/transit/provision), create the route and Border Gateway Protocol report. For more information, see [Generating a route report](/docs/transit-gateway?topic=transit-gateway-route-reports&interface=ui).

## Related links
{: #tgw-adding-connections-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Viewing and deleting {{site.data.keyword.tg_short}} connections](/docs/vmware-service?topic=vmware-service-tgw-viewing-deleting-connections)
* [Getting help and support for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-support)
