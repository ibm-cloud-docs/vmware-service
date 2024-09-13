---

subcollection: vmware-service
copyright:
  years: 2024
lastupdated: "2024-09-13"

content-type: tutorial
services: vmware-service
account-plan: paid
completion-time: 30m


---

{{site.data.keyword.attribute-definition-list}}
{:video: .video}

# Configuring disaster recovery with VMware Cloud Director Availability
{: #vcda-creating-dr-config}
{: toc-content-type="tutorial"}
{: toc-services="vmware-service"}
{: toc-completion-time="30m"}

When you install VMware Cloud Director Availability (VCDA) on a {{site.data.keyword.vcf-aas-full}} instance, you can create a disaster recovery configuration. Using the VCDA service, you can replicate the primary production workload environment over to a failover environment during an unplanned service interruption. When the interruption resolves, the workload moves back to the primary environment. Find out how to use {{site.data.keyword.vcf-aas}} with VCDA to create a disaster recovery configuration in the following video.

![Create a disaster recovery configuration](https://www.kaltura.com/p/1773841/sp/177384100/embedIframeJs/uiconf_id/27941801/partner_id/1773841?iframeembed=true&entry_id=1_0xgcli85){: video output="iframe" data-script="none" id="mediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}.

## Objectives
{: #vcda-creating-dr-config-objectives}

In this tutorial, you learn how to create a disaster recovery configuration that uses a {{site.data.keyword.vcf-aas}} single-tenant instance as the primary workload environment and a {{site.data.keyword.vcf-aas}} multitenant instance as the disaster recovery environment.

## Before you begin
{: #vcda-creating-dr-config-prereq}

The VCDA service is optionally included in your single-tenant {{site.data.keyword.vcf-aas}} Cloud Director site order and included by default on all multitenant virtual data centers (VDCs).

For a VCDA disaster recovery configuration, a monthly charge is incurred per protected virtual machine (VM).

This tutorial requires:

* An {{site.data.keyword.cloud_notm}} [billable account](/docs/account?topic=account-accounts).
* Required user permissions. Make sure that your user account has sufficient permissions [to create and manage {{site.data.keyword.vcf-aas}} resources](/docs/vmware-service?topic=vmware-service-getting-started).
* [A preprovisioned {{site.data.keyword.vcf-aas}} single-tenant Cloud Director site](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering).
* [The VCDA service is installed on your primary single-tenant Cloud Director site instance](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting).
* Identify the {{site.data.keyword.vcf-aas}} multitenant Cloud Director site that you plan to use as the disaster recovery site.

From your browser, open a tab for the *primary* single-tenant Cloud Director site details page and a tab for the *disaster recovery* multitenant Cloud Director site details page.
{: recommendation}

## Create a pairing between the primary instance and the disaster recovery instance
{: #vcda-creating-dr-config-pairing}
{: step}



1. From the VMware Solutions console, go to the Cloud Director site details page to open the VCDA service for your single-tenant and multitenant instances. 
   1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud director sites** tab.
   1. Click the *primary* single-tenant Cloud Director site to open the details page.
   1. Click the **Add-on services** tab and expand the **VMware Cloud Director Availability** service to view the service details page.
   1. Repeat the previous steps in a new browser tab to go to the *disaster recovery* multitenant Cloud Director site details page.
   1. Return to the browser tab for the *primary* single-tenant site.
1. Create the instance pairing for the *primary* site to the *disaster recovery* site. 
   1. From the **Instance endpoints and connections** section of the VCDA details page for the *primary* site, click the **{{site.data.keyword.vcf-aas}} pairings** tab. Then, click **Create pairing**.
   1. On the **Create connection** panel, complete the following configuration.
      - For **Zones**, select the data center for the *primary* site VDC.
      - For **Peer geography** and **Peer region**, select the geography and region for the *disaster recovery* site.
      - For **Peer site name**, go to the **Instance endpoints and connections** section of the VCDA service details page for the *disaster recovery* site and complete the following steps.
      1. On the **Instance endpoints** tab, click the **Copy to clipboard** icon for the **Site name** for the instance to pair.
      1. Return to the **Create connection** panel for the *primary* site and paste the disaster recovery site name in the **Peer site name** field.
   1. Click **Create pairing**.
1. Create the instance pairing for the *disaster recovery* site to the *primary* site.
   1. From the **Instance endpoints and connections** section of the VCDA details page for the *disaster recovery* site, click the **{{site.data.keyword.vcf-aas}} pairings** tab. Then, click **Create pairing**.
   1. On the **Create connection** panel, complete the following configuration.
      - For **Zones**, select the data center for the *disaster recovery* site VDC.
      - For **Peer geography** and **Peer region**, select the geography and region for the *primary* site.
      - For **Peer site name**, go to the **Instance endpoints and connections** section of the VCDA service details page for the *primary* site and complete the following steps.
      1. On the **Instance endpoints** tab, click the **Copy to clipboard** icon for the **Site name** for the instance to pair.
      1. Return to the **Create connection** panel for the *disaster recovery* site and paste the primary site name in the **Peer site name** field.
   1. Click **Create pairing**.
1. Return to the **Instance endpoints and connections** section of the VCDA details page for the *primary* site and click the **{{site.data.keyword.vcf-aas}} pairings** tab. The **Waiting for peer pairing** status is displayed for the new pairing.
1. When the pairing status is **Available**, click **Open VCDA** to start the VMware Cloud Director VCDA console for the *primary* site.

## Configure the disaster recovery policy
{: #vcda-creating-dr-config-drplan}
{: step}

1. Log in to the destination site for the disaster plan.
   1. From the VCDA console for the *primary* site, click **Peer Sites** and select the *disaster recovery* peer site in the **Peer Sites** table.
   1. Click **LOGIN**. 
   1. Return to the VMware Solutions console browser tab for the *disaster recovery* instance and click **VMware console** to open the VMware Cloud Director console.
   1. From the VMware console, select the *disaster recovery* VDC.
   1. From the top of the **Virtual Machines** page, copy the **Organization:** ID.
   1. Return to the VCDA console browser tab for the *primary* site and click **OTHER AUTHENTICATION METHODS > Use challenge authentication** on the **Log In** window.
   1. Paste the *disaster recover* site Organization ID in the **Organization:** field and click **GENERATE NEW CHALLENGE**. Then, click **LOGIN**.
   1. On the **Approve Remote Login** page, click **APPROVE**.
1. Configure the outgoing replications for the disaster plan.
   1. Click **Outgoing Replications**. Notice that the *disaster recovery* site credentials in the **Destination site** field confirm the location for the outgoing replications.
   1. Click the **New protection** icon above the **Outgoing Replications** table and complete the following steps in the **New Outgoing Protection** window.
      1. For the source, select the VMs or vApps to protect and click **Next**.
      1. For the destination, select the *disaster recovery* VDC and the storage policy for where the protected VMs are replicated. Then, click **Next**.
      1. For the settings, select a default SLA profile or manually configure the protection settings and click **Next**.
      1. Review the configuration settings and click **FINISH**.

    The configuration for the new protection completes, then synchronizes the data in the disaster recovery protection site to the destination site. The synchronization time depends on the size and number of VMs or vApps in the site. The synchronization is complete when the date and time display in the **Last changed** column of the **Outgoing Replications** table. Select the outgoing replication protection VM to review the tabs for the configuration details and the replication instances.

1. Review the *disaster recovery* destination replication to confirm the protection.
   1. From the VCDA console, click **Incoming Replications**.
   1. Select the *disaster recovery* protection configuration in the **Incoming Replications** table to review the replication instances.

## Complete the failover to the disaster recovery site
{: #vcda-creating-dr-config-failover}
{: step}

1. From the VCDA console for the *primary* site, click **Outgoing Replications**.
1. Select the *disaster recovery* protection configuration and select **ALL ACTIONS > Failover**.
1. On the **Failover** window, create the following configuration.
   1. For **Settings**, use the default options and click **NEXT**.
   1. For **Recovery instance**, select the replicated instance and click **NEXT**.
   1. Review the failover configuration and click **FINISH**. The data synchronizes and the recovery state displays **Failed-Over**. The workload is now active in the *disaster recovery* site.

## Complete the recovery for the primary site
{: #vcda-creating-dr-config-failback}
{: step}

1. Select the protection.
   1. From the VCDA console for the *primary* site, select **Outgoing Replications**.
   1. Select the *disaster recovery* protection configuration and click **ALL ACTIONS > Reverse**.
   1. Click **REVERSE** to confirm the configuration. The replication now uses the *disaster recovery* site as the source and the *primary* site as the destination.
1. Move the active workload back to the *primary* site.
   1. From the VCDA console for the *primary* site, select **Incoming Replications**.
   1. Select the *disaster recovery* protection configuration and select **ALL ACTIONS > Failover**.
       On the **Failover** window, create the following configuration.
      1. For **Settings**, use the default options and click **NEXT**.
      1. For **Recovery instance**, select the replicated instance and click **NEXT**.
      1. Review the failover configuration and click **FINISH**. The data synchronizes and the recovery state displays **Failed-Back**. The workload in now back on the *primary* site.



