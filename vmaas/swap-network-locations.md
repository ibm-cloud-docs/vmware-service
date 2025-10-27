---

copyright:

  years: 2025

lastupdated: "2025-10-24"

keywords: swap network location, highly available network, network edge, regional high availability

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Swapping locations for a regional high availability edge
{: #swap-network-locations}

{{site.data.content.vms-deprecated-note}}

You can swap the primary and secondary network locations for a regional high availability edge on the virtual data center summary page.

The primary networking location is the preferred location for your workloads. During an outage at the primary location, the secondary location temporarily becomes the active location.

## Procedure to swap locations for a highly available network edge
{: #swap-network-locations-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the highly available virtual data center name.
3. In the network location section of the **Summary** tab, click **Swap primary and secondary** to change the locations of your workloads.
4. Review the location swap and click **Confirm**.

## Related links
{: #swap-network-locations-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} virtual data centers](/docs/vmware-service?topic=vmware-service-tenant-viewing-vdc)
