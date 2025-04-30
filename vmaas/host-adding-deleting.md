---

copyright:

  years: 2022, 2025

lastupdated: "2025-04-30"

keywords: add host, delete host, host adding, host remove

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Adding and deleting hosts
{: #host-adding-deleting}

You can add or delete hosts to and from a *single-tenant* cluster.

For stretched vSAN™ high availability clusters, the hosts are split into the first and second location of the resource pool. The minimum host requirement for stretched vSAN high availability clusters is 14.

## Procedure to add and delete hosts
{: #host-adding-deleting-proc}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-aas}}** from the left navigation panel.
2. On the **{{site.data.keyword.vmware-service_short}}** page, click the single-tenant Cloud Director site name.
3. Click the **Resource pool** tab.
4. Locate the resource pool where you want to add hosts and expand the cluster section.
5. Locate the cluster to update and click **Actions > Edit host quantity**.
6. In the **Edit host quantity** pane, increase or decrease the current host quantity.
7. Review the new cost, select the confirmation checkbox, and click **Change** to confirm.

## Related links
{: #host-adding-deleting-links}

* [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy)
* [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering)
* [Viewing and deleting {{site.data.keyword.vcf-aas}} Cloud Director sites](/docs/vmware-service?topic=vmware-service-tenant-viewing-sites)
