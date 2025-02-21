---

copyright:

  years:  2023, 2025

lastupdated: "2025-02-13"

keywords: IAM user, user role, user permission, IAM VMware Cloud Director

subcollection: vmware-service


---

{{site.data.keyword.attribute-definition-list}}

# Roles and permissions for VMware Cloud Director
{: #vmaas-iam_vcd}

The following table provides information about the platform management roles and permissions for {{site.data.keyword.vmware-service_full}}.

* **Minimum** - roles with the bare minimum permissions in VMware Cloud Director™.
* **VMware Cloud Director** - roles that are provided by VMware Cloud Director. For more information, see [Rights in predefined global tenant roles](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director/vmware-cloud-director/10-6.html#GUID-AE42A8F6-868C-4FC0-B224-87CA0F3D6350){: external}.
* **Custom** - roles that are custom-defined by {{site.data.keyword.IBM}}.

| Platform management role | Actions | Level of permission |
|:----------------- |:----------------- |:----------------- |
| Reader | Read-only actions to view service-specific resources. | Minimum |
| Writer | Create and edit service-specific resources. | Minimum |
| Manager | Privileged actions as defined by the service in addition to create and edit service-specific resources. | Custom |
| Viewer | Read-only actions to view the summary and details of instances. | Minimum |
| Operator | Read-only actions. For example, list instances and view instance details. | Minimum |
| Editor | Update a specific instance. For example, add or remove VMware ESXi™ servers, clusters, and services; upgrade an instance to a higher version. | Minimum |
| Administrator | Full management access. For example, create new instances, delete instances, and grant platform access to other users.| Custom |
| VCFaaS Full Viewer | All view access to every component in VMware Cloud Director. | Custom |
| VCFaaS vApp Author | Use catalogs and create vApps in VMware Cloud Director. | VMware Cloud Director |
| VCFaaS vApp User | Use existing vApps in VMware Cloud Director. | VMware Cloud Director |
| VCFaaS Catalog Author | Create and publish catalogs in VMware Cloud Director. | VMware Cloud Director |
| VCFaaS Network Admin | Create, view, edit, delete the subnet, the static route, and troubleshoot routing in VMware Cloud Director. | Custom |
| VCFaaS Console User | View a virtual machine state, properties, and use the guest operating system in VMware Cloud Director. | VMware Cloud Director |
| VCFaaS Backup User | Manage Veeam® backup jobs in VMware Cloud Director. | Custom |
| VCFaaS Security Admin | View and edit the edge firewall and the distributed firewall in VMware Cloud Director. | Custom |
{: caption="Roles and actions for {{site.data.keyword.vcf-aas}}" caption-side="bottom"}

## Recently introduced rights
{: #vmaas-iam_vcd-custom-reqs}

Additional rights are available with recent releases. If you use pre-configured Open ID Connect (OIDC) roles or any role other than the Organization Administrator role, you must manually add these rights to your roles.

To update the roles with the new rights, complete the following steps as an **IBM Cloud IAM Administrator** or as an **Organization Administrator**.

1. From the tenant portal, click the **Menu** icon at the upper left of the page and select **Administration**.
2. Under the **Access Control** section in the left pane, select **Roles**.
3. Select the role to change and click **Edit**. You must use the recommended OIDC roles from the following table, **Table 2. Recommended OIDC roles**, or use customized roles.
4. In the **Edit Role** window, select the new permissions and clear the permissions to remove. You can add the new tenant permissions to the roles as defined in **Table 2. Recommended OIDC roles**.
5. Click **SAVE** to apply the new or removed permissions. You might need to log out and log back into the tenant portal to see the changes.
6. Repeat for each role that requires the update.

For more information, see [Edit a Custom Tenant Role Using Your VMware Cloud Director Tenant Portal](https://techdocs.broadcom.com/us/en/vmware-cis/cloud-director/vmware-cloud-director/10-5/map-for-vmware-cloud-director-tenant-portal-guide-10-5/managing-users-groups-and-roles-in-vcd-tenant/vcd-roles-and-rights-tenant/edit-a-role-using-your-vcd-tenant-portal-tenant.html).{: external}

The permissions that include an asterisk (*) are introduced in VMware Cloud Director 10.6 and are available to users after the Cloud Director site where the virtual data centers are deployed is upgraded to VMware Cloud Director 10.6.0.1. For more information, see [IBM Cloud Maintenance notifications for scheduled upgrade dates](https://cloud.ibm.com/notifications?type=maintenance).
{: note}

The following table provides the recently introduced rights and the recommended OIDC roles to manually update.

| Permission | Manager | Administrator | Director Full Viewer | Director Network Admin | Director Security Admin |
|:--------------|:---------------|:---------------|:---------------|:---------------|:-----------------|
| IP Spaces: Allocate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) |  ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Gateway: Configure Firewall | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure NAT | | | | | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Gateway: Configure System Logging | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Gateway: View | | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Network: Manage Manual IP Reservation* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Private IP Spaces: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Private IP Spaces: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway: Simple View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway BGP: Simple Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway BGP: Simple View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Firewall: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Firewall: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway IP Sec VPN: Manage* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway IP Sec VPN: View* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway NAT: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway NAT: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Routing: Simple View* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Network: View | | | ![Available](../../icons/checkmark-icon.svg) | | |
{: caption="Recommended OIDC roles" caption-side="bottom"}

## Custom-defined roles and permissions
{: #vmaas-iam_vcd-custom}

The following table provides information about roles that are custom-defined by IBM.

| Permission | Manager | Administrator | Director Full Viewer | Director Network Admin | Director Security Admin | Director Backup User |
|:--------------|:---------------|:---------------|:---------------|:---------------|:-----------------|:---------------|
| Access Control List: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | ![Available](../../icons/checkmark-icon.svg) |  |
| Access Control List: View  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |
| Access All Organization VDCs | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Alternate Admin Entity: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) |  |
| API Explorer: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| API Tokens: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| API Tokens: Manage All | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Add vApp from My Cloud | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Change Owner | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: CLSP Publish Subscribe | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Create / Delete a Catalog | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Publish | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: Shadow VM View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| Catalog: Sharing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: VCSP Publish Subscribe | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: VCSP Publish Subscribe Caching | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Catalog: View ACL | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Catalog: View Private and Shared Catalogs | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| Catalog: View Published Catalogs | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |![Available](../../icons/checkmark-icon.svg) | | |
| Certificate Library: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Certificate Library: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Custom entity: View all custom entity instances in org | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| Custom entity: View custom entity instance | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| Extension Service API Definition: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | | |
| Extension Service API Definition: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | |
| Extension Services: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | |
| Extensions: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | |
| External Service: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | | |
| External Service: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | |
| General: Administrator Control | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |  | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| General: Administrator View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| General: Send Notification | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| General: View Error Details | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Group / User: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Group / User: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Hybrid Cloud Operations: Acquire control ticket | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Acquire from-the-cloud tunnel ticket | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Acquire to-the-cloud tunnel ticket | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Create from-the-cloud tunnel | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Create to-the-cloud tunnel | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Delete from-the-cloud tunnel | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Delete to-the-cloud tunnel | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Hybrid Cloud Operations: Update from-the-cloud tunnel endpoint tag | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| IP Spaces: Allocate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Localization Resources: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Metadata File Entry: Create/Modify | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Network Pool: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Object Extensions: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  |  | |
| Object Extensions: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | |
| Organization Network: Create or Delete | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization Network: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization Network: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Compute Policy: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Disk: View IOPS| ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Distributed Firewall: Configure Rules | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Distributed Firewall: View Rules | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure BGP Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure DHCP | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure DNS | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure ECMP Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure Firewall | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure IPSec VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure L2 VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure Load Balancer | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure NAT | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure OSPF Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure Remote Access | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure Route Advertisement | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure SLAAC Profile | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure SSL VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Configure Static Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure Syslog | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Configure System Logging | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: Convert to Advanced Networking | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: Distributed Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View BGP Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Gateway: View DHCP | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View DNS | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View Firewall | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View IPSec VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View L2 VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View Load Balancer | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View NAT | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View OSPF Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View Remote Access | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View Route Advertisement | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View SLAAC Profile | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View SSL VPN | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Gateway: View Static Routing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Named Disk: Change Owner | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Named Disk: Create | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Named Disk: Delete | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Named Disk: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Named Disk: Move | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Named Disk: View Encryption Status | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Named Disk: View Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Network: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| Organization vDC Network: Manage Manual IP Reservation* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC Network: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Network: View Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Organization vDC Storage Policy: View Capabilities | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Storage Profile: Set Default | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC: Edit | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC: Edit ACL | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC: Manage Firewall | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC: Simple Edit | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC: User View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC: View ACL | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC: View CPU and Memory Reservation | ![Available](../../icons/checkmark-icon.svg) |![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization VDC: view metrics | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization vDC: VM-VM Affinity Edit | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization vDC Shared Named Disk: Create | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Association Settings | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Federation Settings | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Leases Policy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit OAuth Settings | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Password Policy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit Quotas Policy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Edit SMTP Settings | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Import User/Group from IdP while Editing VDC ACL | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Organization: Perform Administrator Queries | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Organization: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| Organization: view metrics | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | |
| Private IP Spaces: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Private IP Spaces: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Provider Gateway: Simple View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Provider Gateway BGP: Simple View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Firewall: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Firewall: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway IP Sec VPN: Manage* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway IP Sec VPN: View* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway NAT: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway NAT: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Gateway Routing: Simple View* | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Provider Network: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| Resource Pool: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| Quota Policy Capabilities: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Resource Class Action: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  |  | |
| Resource Class Action: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | |
| Role: Create, Edit, Delete, or Copy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Security Tag Edit | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Selector Extensions: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| Selector Extensions: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Service Authorization: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | | |
| Service Configuration: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | | |
| Service Configuration: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Service Link: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | | |
| Service Link: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Service Resource Type: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | | |
| Service Resource Type: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Service Resource: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  | | | |
| Service Resource: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| Service Library: View service libraries | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| SSL: Test Connection | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| Truststore: Manage | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | ![Available](../../icons/checkmark-icon.svg) | |
| Truststore: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| UI Plugins: Define Upload Modify Delete Associate or Disassociate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |  |  | |  |
| UI Plugins: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| UI Plugins: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| vApp Template / Media: Copy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template / Media: Create / Upload | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template / Media: Edit | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template / Media: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) |
| vApp Template: Add to My Cloud | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template: Change Owner | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template: Checkout | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp Template: Download | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Allow All Extra Config | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Allow Matching Extra Config | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Change Owner | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Copy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Create / Reconfigure | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Delete | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Download | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Edit Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| vApp: Edit VM Compute Policy | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Edit VM CPU | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Edit VM Hard Disk | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Edit VM Memory | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Edit VM Network | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| vApp: Edit VM Properties | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| vApp: Manage VM Password Settings | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Power Operations | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Shadow VM View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| vApp: Sharing | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Snapshot Operations | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Upload | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: Use Console | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| vApp: View ACL | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| vApp: View VM and VM's Disks Encryption Status | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| vApp: View VM metrics | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) |
| vApp: VM Boot Options | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: VM Metadata to vCenter | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| vApp: VM Migrate, Force Undeploy, Relocate, Consolidate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | ![Available](../../icons/checkmark-icon.svg) | | |
| VAPP_VM_METADATA_TO_VCENTER | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| VCD Extension: Register, Unregister, Refresh, Associate or Disassociate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| VCD Extension: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
| VDC Group: Configure | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| VDC Group: Configure Logging | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| VDC Group: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | |
| VDC Template: Instantiate | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | | |
| VDC Template: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | |
| vGPU Profile Consumption: View | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | ![Available](../../icons/checkmark-icon.svg) | | | |
{: caption="Custom-defined roles and permissions for {{site.data.keyword.vcf-aas}}" caption-side="bottom"}

## Related links
{: #vmaas-iam_vcd-links}

* [Managing IAM access for {{site.data.keyword.vcf-aas}}](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui)
