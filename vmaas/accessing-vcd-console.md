---

copyright:

  years:  2022, 2023

lastupdated: "2023-01-26"

keywords: vmware service, access, reset, password resources, access VMware Cloud Director console

subcollection: vmware-service

---

{{site.data.keyword.attribute-definition-list}}

# Accessing the VMware Cloud Director console
{: #accessing-vcd-console}

You can use the VMware Cloud Director console to configure and manage the {{site.data.keyword.vmware-service_full}} virtual data centers (VDCs). VMware® workloads are created, deployed, and managed in the VMware Cloud Director console.

Access the VMware Cloud Director console from the VDC details page to complete the following tasks from the console.

* Virtual machine (VM) templates upload
* vApp and VM deployment and management
* Virtual network creation and management
* Edge configuration and putting VMs on the public and private networks
* User administration

## Before you begin
{: #accessing-vcd-console-prereq}

* The first time that you access the VMware Cloud Director console for the VDC region, you must set the **admin** credentials to generate an initial, complex, and random password. After the first VDC is created, the **VMware Cloud Director console** option is enabled on the VDC details page.
* You do not need to generate an **admin** password for each VDC. Reuse the same password for all VDCs in the same region.

## Procedure to reset the admin password
{: #accessing-vcd-console-reset-proc}

1. On the VDC details page, click **Reset on site level**. You are redirected to the {{site.data.keyword.vmware-service_short}} instances details view that is used to host the VDC.
2. Click the **Reset org admin password** link and select **Reset password**.

## Admin credentials notes
{: #accessing-vcd-console-notes}

* A single **admin** credential per {{site.data.keyword.vmware-service_short}} instance exists. Resetting the credential can impact other users that also authenticate with the **admin** credential.
* {{site.data.keyword.vmware-service_short}} does not store the **admin** password. After a password is generated, you must capture it. If the password is lost or you get locked out of your account, you can generate a new password at any time.

## Procedure to access the VMware Cloud Director console
{: #accessing-vcd-console-procedure}

1. On the VDC details page, click **VMware Cloud Director console** to access the console.
2. Use the **admin** username and password to log in to the VMware Cloud Director console for the first time.

   After the **admin** is logged in to the VMware Cloud Director console, you can create extra users who have roles that allow them to access the VMware Cloud Director console.

## Related links
{: #accessing-vcd-console-links}

* [Adding virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-adding)
* [Viewing and deleting virtual data centers](/docs/vmware-service?topic=vmware-service-vdc-view-delete)
* [Viewing {{site.data.keyword.vmware-service_short}} instances](/docs/vmware-service?topic=vmware-service-tenant-viewing)
