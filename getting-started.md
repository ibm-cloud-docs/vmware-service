---

copyright:

  years: 2022, 2025

lastupdated: "2024-05-23"

keywords: vmware getting started, vmware offerings, vmware service, vmware use cases

subcollection: vmware-service

content-type: tutorial
account-plan: paid
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with {{site.data.keyword.vcf-aas}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="20m"}

In this {{site.data.keyword.vmware-service_full}} tutorial, we take you through the process of ordering a {{site.data.keyword.vcf-aas-full}} instance by using the {{site.data.keyword.vmwaresolutions_short}} user interface. Other operations that you can complete are also listed.
{: shortdesc}

The completion time that is listed for this tutorial considers only the time that you spend ordering the artifacts for a {{site.data.keyword.vcf-aas}} instance on the user interface. It does not consider waiting times for deployments, for example.
{: note}

## Before you begin
{: #getting-started-prereqs}

Before you start to work with {{site.data.keyword.vcf-aas}}, review the following information about browser requirements and users accounts.

### Browser requirements
{: #getting-started-browser-req}

For more information, see [Browsers](/docs/overview?topic=overview-prereqs-platform#browsers-platform).

### User accounts
{: #getting-started-user-accts}

You need an {{site.data.keyword.cloud_notm}} account, which must meet certain requirements.

| Account | Description |
|:------- |:---------- |
| IBMid | By using the **IBMid**, you can have a single login username for all {{site.data.keyword.IBM}} products and services that you use, including {{site.data.keyword.cloud_notm}}. VMware Solutions is provided as an infrastructure solution in the {{site.data.keyword.cloud_notm}} catalog. To access the VMware Solutions console, you must have an **IBMid**. \n \n To use your **IBMid** to log in to the VMware Solutions console, you must associate the **IBMid** with an {{site.data.keyword.cloud_notm}} account. When you log in to the console for the first time, you are guided to either associate your existing **IBMid** with an {{site.data.keyword.cloud_notm}} account, or to sign up for a new {{site.data.keyword.cloud_notm}} account. The new {{site.data.keyword.cloud_notm}} account is automatically associated with your **IBMid**. You need to go through this process only once. \n \n If you have problems when you associate your **IBMid** with an {{site.data.keyword.cloud_notm}} account, see [Why is my password incorrect?](/docs/account?topic=account-ts_logintoibm) |
| {{site.data.keyword.cloud_notm}} account | To order and use {{site.data.keyword.cloud_notm}} services, an {{site.data.keyword.cloud_notm}} account is required. Billing information is associated with the {{site.data.keyword.cloud_notm}} account. The price of the physical and virtual infrastructure and the resulting licenses are charged to your {{site.data.keyword.cloud_notm}} account. |
{: caption="Required user accounts" caption-side="bottom"}

## Accessing the VMware Solutions console
{: #getting-started-step1}
{: step}

The VMware Solutions console is the user interface where you order and manage your deployments. To access the console:

1. Go to https://cloud.ibm.com/vmware.
2. Log in to the console with your **IBMid**.

## Planning the deployment
{: #getting-started-step2}
{: step}

Before you order an instance, consider the required size of the VMware® deployment.

VMware deployments are sized based on the CPU, memory, and storage that are required to run the targeted workload. If you are planning a workload migration from on-premises to the cloud, the on-premises size is a good starting point. VMware deployments are elastic and you can resize them at any time.

After the basic size of the VMware environment is established, consider the {{site.data.keyword.vcf-aas}} deployment type of multitenant or single-tenant instance as well as the configuration options for the instance.

For more information, see [Planning the deployment](/docs/vmware-service?topic=vmware-service-tenant-plan-deploy).

## Ordering a {{site.data.keyword.vcf-aas}} instance
{: #getting-started-step3}
{: step}

Specify your {{site.data.keyword.vcf-aas}} instance settings according to your deployment type.

For single-tenant instances, the following configurations are used to order a new VMware cluster for running the target workload:

* Cloud Director site name and resource group
* Cloud Director site location (geography and region)
* Resource pool name and location
* Optional SAP-certified server profiles
* Cluster name
* Attached Network File Storage (NFS) performance tiers and amount of storage in each tier
* Host profile and quantity
* Public-only or private-only network settings
* Add-on services

After the dedicated Cloud Director site is in **Available** status, you create virtual data centers (VDCs) to deploy on the infrastructure.

For multitenant instances, the following configurations are used to order a new VDC that deploys on an existing {{site.data.keyword.IBM_notm}} owned VMware cluster.

* VDC name and resource group
* Pricing plan for on-demand or reserved resource allocation
* VMware Cloud Director™ site location (region, Cloud Director instance, data center)
* Optional fast provisioning of virtual machines that use linked clones
* Optional network edge types
* vCPU and RAM limits

After you specify all configurations, validate the cost and submit the instance order.

For more information, see [Ordering Cloud Director site instances](/docs/vmware-service?topic=vmware-service-tenant-ordering) and [Ordering virtual data center instances](/docs/vmware-service?topic=vmware-service-vdc-adding).

## Other operations
{: #getting-started-step9}

* [Adding resource pools](/docs/vmware-service?topic=vmware-service-pvdc-adding-deleting)
* [Adding and deleting clusters](/docs/vmware-service?topic=vmware-service-cluster-adding-deleting)
* [Adding and deleting hosts](/docs/vmware-service?topic=vmware-service-host-adding-deleting)
* [Adding and deleting storage](/docs/vmware-service?topic=vmware-service-storage-adding-deleting)
* [Adding, editing, and deleting private-only network subnets](/docs/vmware-service?topic=vmware-service-subnet-adding-deleting)
* [Adding and deleting capacity](/docs/vmware-service?topic=vmware-service-capacity-adding-deleting)
