---

copyright:

  years: 2023, 2024

lastupdated: "2024-10-10"

keywords: create VMware Cloud Foundation as a Service pairing, pairing

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Creating and deleting {{site.data.keyword.vcf-aas}} pairings with VCDA
{: #vcda-creating-deleting-vmaas-pairing}

When VMware Cloud Director Availability (VCDA) is enabled, you can create cloud-to-cloud connections between your instance and other single-tenant and multitenant {{site.data.keyword.vmware-service_full}} instances. You must create a pairing from both Cloud Director sites to connect.

VMware Shared pairings are automatically created when you install VCDA on a {{site.data.keyword.vcf-aas-full}} instance. For more information, see [Migrating VMware Shared workloads to {{site.data.keyword.vcf-aas}} with cloud-to-cloud connections](/docs/vmware-service?topic=vmware-service-vcda-migrating-cloudtocloud-shared).
{: note}

## Procedure to create a {{site.data.keyword.vcf-aas}} pairing
{: #vcda-creating-deleting-vmaas-pairing-proc-add}



1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane. {: #step-1}
1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click an instance name.
1. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
1. On the **{{site.data.keyword.vcf-aas}} pairings** tab, click **Create pairing**.
1. On the **Create connection** panel, complete the following configuration.
   1. For **Zones**, the default zone of the resource pool is displayed. If the instance has multiple PVDCs belonging to different zones, all the zones are displayed. Select the zone pairing.
   1. For **Peer geography**, the geography where the peer site is installed is displayed.
   1. For **Peer site name**, return to the VMware Cloud Director Availability details page and click the **Instance endpoints** tab. Click the **Copy to clipboard** icon for the **Site name** for the instance to pair. Paste the site name in the create connection configuration.
   1. For **Peer region**, select the region where the peer site is installed.
   1. For **Administrator notes**, you can enter notes to provide more information for the pairing. The maximum length is 200 characters and the % & < > " ' / characters are not supported.
1. Click **Create pairing**. The **Creating** status displays.

   When the **Waiting for peer pairing status** displays, repeat the previous steps to complete the pairing connection with the Cloud Director site to pair.

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
1. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click an instance name to pair with the first pairing.
1. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
1. On the **{{site.data.keyword.vcf-aas}} pairings** tab, click **Create pairing**.
1. On the **Create connection** panel, complete the following configuration.
   1. For **Zones**, the default zone of the resource pool is displayed. If the instance has multiple PVDCs belonging to different zones, all the zones are displayed. Select the zone pairing.
   1. For **Peer geography**, the geography where the peer site is installed is displayed.
   1. For **Peer site name**, return to the VMware Cloud Director Availability details page and click the **{{site.data.keyword.vcf-aas}} pairings** tab. Click the **Copy to clipboard** icon for the **Peer site name** that you created for the first pairing. Paste the site name in the create connection configuration.
   1. For **Peer region**, select the region of the first pairing.
   1. For **Administrator notes**, you can enter notes to provide more information for the pairing. The maximum length is 200 characters and the % & < > " ' / characters are not supported.
1. Click **Create pairing**. The **Available** status displays when the pairing is complete.

The following pairing status options are available.

| Status | Description |
|:---- |:----------- |
| Creating | The pairing task starts. |
| Waiting for peer pairing | The pairing is complete on one site. |
| Available | The pairing is complete on both sites. |
{: caption="Pairing status" caption-side="bottom"}

## Procedure to delete a {{site.data.keyword.vcf-aas}} pairing
{: #vcda-creating-deleting-vmaas-pairing-proc-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation pane.
2. In the **{{site.data.keyword.vmware-service_short}}** table, click the **Cloud Director site** tab, then click an instance name.
3. Click the **Add-on services** tab, then expand the **VMware Cloud Director Availability** service.
4. On the **{{site.data.keyword.vcf-aas}} pairings** tab, locate the pairing to delete.
5. Click the overflow menu and click **Delete pairing**.

## Related links
{: #vcda-creating-deleting-vmaas-pairing-links}

* [Migrating {{site.data.keyword.vcf-aas}} workloads with cloud-to-cloud connections](/docs/vmware-service?topic=vmware-service-vcda-migrating-cloudtocloud-vmaas)
* [Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Protecting workload data in {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda)
* [Viewing VCDA details](/docs/vmware-service?topic=vmware-service-vcda-viewing)
* [Adding and deleting VCDA](/docs/vmware-service?topic=vmware-service-vcda-adding-deleting)
