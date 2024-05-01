---
subcollection: vmware-service
copyright:
  years: 2023, 2024
lastupdated: "2024-04-09"

content-type: tutorial
services: vmware-service
account-plan: paid
completion-time: 30m

---
{{site.data.keyword.attribute-definition-list}}

# Using OVFTool to import VMs to {{site.data.keyword.vcf-aas}}
{: #vmwaas-ovftool}
{: toc-content-type="tutorial"}
{: toc-services="vmware-service"}
{: toc-completion-time="30m"}

The {{site.data.keyword.vmware-service-full}} is a powerful platform to manage virtualized resources and to facilitate the creation of flexible cloud environments. The VMware Open Virtualization Format Tool (OVFTool) simplifies the tasks of deploying and configuring virtual appliances within the VMware Cloud Director system.

This tutorial provides an overview of using OVFTool to manage virtual appliances on VMware Cloud Director.

## Objectives
{: #vmwaas-ovftool-objectives}

The objective of this tutorial is to demonstrate the basic steps to import an OVA image from your on-premises environment into a {{site.data.keyword.vcf-aas-full}} single-tenant or multitenant instance after initial provisioning.

This tutorial takes approximately 20-30 minutes to complete and assumes that a [{{site.data.keyword.vcf-aas}} instance](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering) and [a virtual data center (VDC)](/docs/vmwaresolutions?topic=vmwaresolutions-vdc-adding) are provisioned.

In this tutorial, you will learn:

* How to create a local user in a VMware Cloud Director instance.
* How to import an OVA image into a VMware Cloud Director instance by using OVFTool.

## Before you begin
{: #vmwaas-ovftool-prereqs}

OVFTool is available without charge. You need to create a VMware account to [download OVFTool](https://customerconnect.vmware.com/downloads/get-download?downloadGroup=OVFTOOL460){: external}.

This tutorial requires:

* An {{site.data.keyword.cloud_notm}} [billable account](/docs/account?topic=account-accounts).
* Required user permissions. Ensure that your user account has sufficient permissions [to create and manage {{site.data.keyword.vcf-aas}} resources](/docs/vmware-service?topic=vmware-service-getting-started).
* [A preprovisioned {{site.data.keyword.vcf-aas}} instance](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering).
* [A preprovisioned VDC on {{site.data.keyword.vcf-aas}}](/docs/vmwaresolutions?topic=vmwaresolutions-vdc-adding).
* [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* An [{{site.data.keyword.cloud_notm}} API key](/docs/account?topic=account-userapikey&interface=ui).
* An exported VM (virtual machine) to import into a VMware Cloud Director instance in OVA format. For more information, see [Deploy and export OVF and OVA templates](https://docs.vmware.com/en/VMware-vSphere/8.0/vsphere-vm-administration/GUID-AFEDC48B-C96F-4088-9C1F-4F0A30E965DE.html){: external}.

## Creating a local username and password in VMware Cloud Director
{: #vmwaas-ovftool-localuser}
{: step}

A local user in this tutorial is used to authenticate when you import the OVA into the {{site.data.keyword.vcf-aas}} instance.

To create a local username and password in VMware Cloud Director, complete the following steps:

1. Log in to the {{site.data.keyword.vcf-aas}} instance with a user that has the `Organization Administrator` role.
2. In the navigation bar, click **Administration**.
3. In the left pane, under **Access Control**, click **Users**.
4. Next to the list of users, click **New**.
5. Enter a username and password for the user. The minimum password length is 6 characters.
6. From the list of predefined roles, select the `Organization Administrator` role to assign to the user.
7. Click **Save**.

## Uploading an OVA image into a VDC
{: #vmwaas-ovftool-upload}
{: step}

To upload an OVA image into a VDC, complete the following steps:

1. Install [OVFTool](https://customerconnect.vmware.com/downloads/get-download?downloadGroup=OVFTOOL460){: external} on your local computer.
2. To upload a VM image into a vDC, use the following command. After upload, the VM image appears in a vApp and is ready for configuration.

```bash
ovftool -tt=vCloud c:\<LOCAL_FILEPATH>\<FILE_NAME>.ova “vcloud://<ORG_USER>@<VCLOUD_URL>/cloud?org=<ORG_NAME>&vdc=<VDC_NAME>&vapp=<VAPP_NAME>”
```

In the previous command, replace the variables with the following values:

* <LOCAL_FILEPATH> is the absolute file path that contains the OVA image.
* <FILE_NAME> is the name of the OVA image.
* <ORG_USER> is the local username (local) to log in to VMware Cloud Director. OVFTool prompts you for the password.
* <VCLOUD_URL> is the URL that you use to log in to VMware Cloud Director. Use only the domain name, for example, `https://dirw003.us-east.vmware.cloud.ibm.com/`.
* <ORG_NAME> is the full name of your VMware Cloud Director organization.
* <VDC_NAME> is the full name of your VDC.
* <VAPP_NAME> is the name of the destination vApp.

Example command:

```bash
.\ovftool.exe -tt=vCloud c:\test-image.ova vcloud://local-admin@"dirw003.us-east.vmware.cloud.ibm.com/cloud?org=xxxxxa&vdc=yyyyyo&vapp=demoApp"
Opening OVA source: c:\test-image.ova
The manifest validates
Enter login information for target vcloud://dirw003.us-east.vmware.cloud.ibm.com/xxxxxx
Username: local-admin
Password: **********
Opening vCloud target: vcloud://local-admin@dirw003.us-east.vmware.cloud.ibm.com:443/cloud
Deploying to vCloud vApp: vcloud://local-admin@dirw003.us-east.vmware.cloud.ibm.com:443/cloud
Transfer Completed
Completed successfully
```
The result is a vApp within the {{site.data.keyword.vcf-aas}} instance that can be started.
