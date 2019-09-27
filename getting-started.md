---

copyright:
  years: 2019
lastupdated: "2019-09-25"

keywords: getting started tutorial, getting started, Cloud Pak for Applications, Kabanero, icp, icpa, icp4a, ocp, openshift, was, mobile, runtime, container

subcollection: cloud-pak-applications

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Getting started with {{site.data.keyword.icpa_short}}
{: #getting-started}

{{site.data.keyword.icpa_rm}} is an enterprise-ready, containerized software solution for modernizing existing applications and developing new cloud-native apps that run on Red Hat&reg; OpenShift&reg;. This hybrid, multicloud foundation breaks down technology and data silos to make modernization faster and more secure, and speeds development of applications built for Kubernetes. You can access cloud services and meet the technology standards and policies your company requires.
{: shortdesc}

## What's inside this Cloud Pak
{: #whatsinside}
{{site.data.keyword.icpa_short}} includes the following products:

| Product | Description |
| ------- | ----------- |
| **IBM WebSphere Application Server** | Industry-leading, production-ready, standards-based Java™ EE-compliant architectures |
| **Red Hat OpenShift Container Platform** |  A comprehensive solution for hybrid cloud, enterprise container, and Kubernetes development and deployments |
| **{{site.data.keyword.ke}}** | The commercial, enterprise-ready, and fully supported implementation of the Kabanero.io open source community project |
| **Red Hat Runtimes** | Open runtimes, tools, and components for developing and maintaining cloud-native applications |
| **IBM Mobile Foundation** | An industry-leading, secured platform for developing and deploying the next generation of digital apps |
| **IBM Modernization &amp; Developer Tools** | Tools to assist with your move to the cloud |
| **IBM Cloud Private** | A private cloud platform that provides the benefits of the public cloud from the safety of your firewall-protected data center |

For more information about these products, see the **Key offerings** section of the [About](cloud-pak-applications?topic=cloud-pak-applications-about) page.

## Before you begin
{: #prereqs}
Before you can install the Cloud Pak, you must purchase a license through
[IBM Passport Advantage  ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/software/passportadvantage/index.html){:new_window}.
The part numbers for {{site.data.keyword.icpa_short}} are as follows.  You can have one installation of {{site.data.keyword.icpa_short}} per license.

| Part Number | Description |
| ----------- | ----------- |
| D24XJLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE LICENSE + SW SUBSCRIPTION & SUPPORT 12 MONTHS |
| D24XLLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE FOR IBM Z LICENSE + SW SUBSCRIPTION & SUPPORT 12 MONTHS |
| E0QB6LL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE ANNUAL SW SUBSCRIPTION & SUPPORT RENEWAL |
| E0QB7LL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE FOR IBM Z ANNUAL SW SUBSCRIPTION & SUPPORT RENEWAL |
| D24XKLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE SW SUBSCRIPTION & SUPPORT REINSTATEMENT 12 MONTHS |
| D24XMLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE FOR IBM Z SW SUBSCRIPTION & SUPPORT REINSTATEMENT 12 MONTHS |
| D24XNLL | IBM Cloud Pak for Applications Virtual Processor Core Trade Up from Prior Programs |
| D24XPLL | IBM Cloud Pak for Applications Virtual Processor Core for IBM Z Trade Up from Prior Programs |
| D24XHLL | IBM CLOUD PAK FOR APPLICATIONS VPC MONTHLY LICENSE |
| D24XILL | IBM CLOUD PAK FOR APPLICATIONS VPC MONTHLY LICENSE |


Make sure that you have a Red Hat OpenShift cluster, and make sure that it meets the minimum scheduling capacity:

| Software | Memory (GB) | CPU (cores) | Disk (GB) | Nodes |
| -------- | ----------- | ----------- | --------- | ----- |
| {{site.data.keyword.ke_notm}} | 20 | 8 | 25 | 2 |
| {{site.data.keyword.ta}} | 6 | 3 | 8 |  |
| **Total** | **26** | **11** | **33** | **2** |

If you do not have a cluster, create one and then return to the {{site.data.keyword.icpa_short}} page.

Also, ensure that you have the proper IBM Cloud Identity and Access Management (IAM) permissions:

| Service or Resource | IAM Role(s) |
| ----------------- | ------------------- |
| 'Kubernetes Cluster' service | Manager and Writer |
| Resource Group containing the OCP cluster | Viewer |
| 'License and Entitlement' service | Editor |
| 'Schematics' service | Manager |

For more information on IAM roles and permissions, see [Managing identity and access](https://cloud.ibm.com/docs/iam?topic=iam-userroles).

## Step 1. Configure your installation environment
{: step1}
Select a target cluster, and then select or type a name for your project in the **Project** field.

You can view existing installations of {{site.data.keyword.icpa_short}} by expanding **View existing installations**.

## Step 2. Configure your workspace
{: step2}
In this step, define how your installation is managed in a Schematics workspace.

You can type a name for the installation in the **Name** field, or use the default.  To view your existing resources,
see the [resource list page](https://cloud.ibm.com/resources).

Select a resource group from the **Resource group** list, or use the default.  For more information on resource
groups, see [Best practices for organizing resources in a resource group](https://cloud.ibm.com/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).

Enter any tags you want to use to organize this resource in the **Tags** field in a comma-separated list.  Tags can
contain special characters, which can be used in creating key-value pairs (e.g., key:value) for grouping related tags. Tags are visible across the account.

## Step 3. Complete the pre-installation
{: step3}
Run the preinstallation script. Only a cluster administrator can run the script. If you do not have the proper role on the cluster, click **Share link** to share the preinstallation script with your cluster administrator. Otherwise, click **Run script** to execute the script. Confirm that the script completed successfully.

## Step 4. Set the deployment values
{: step4}
Ensure that an entitlement is assigned.  If not, get an entitlement from IBM Passport Advantage.

Confirm your agreement to the Third-Party Service Agreements by checking the box.

Set the `consoleRoutePrefix` parameter.  This value is used as the subdomain in the URL for the {{site.data.keyword.icpa_short}} landing page; the remainder of the URL is the OpenShift Cluster Console URL.

## Step 5. Install the Cloud Pak
{: step5}
Click **Install**.

## Step 6. Next steps
{: step6}
After the installation completes, links to your {{site.data.keyword.icpa_short}} landing page, your Tekton Dashboard, and your {{site.data.keyword.ta_short}} UI are provided.  You can click the **View log** link and find them at the bottom of the log file, or through the UI:

1. Login to the OpenShift console.
1. Click **Service Catalog**, then select **Application Console**.  You should see several projects installed.
   - If you click the **kabanero** project, the Overview tab contains the URLs to the **icpa-landing** page and the **tekton-dashboard**.
   - If you click the **ta** project, the Overview tab contains the URL to the {{site.data.keyword.ta_short}} UI.
