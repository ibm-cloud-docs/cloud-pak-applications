---

copyright:
  years: 2019
lastupdated: "2019-11-1"

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

{{site.data.keyword.icpa_rm}} is an enterprise-ready, containerized software solution for modernizing existing applications and developing new cloud-native apps that run on Red Hat&reg; OpenShift&reg;. This hybrid, multicloud foundation breaks down technology and data silos to make modernization faster and more secure, and speeds development of applications built for Kubernetes. You can access cloud services and meet the technology standards and policies your company requires. With IBM Mobile Foundation in this Cloud Pak, developers get a secured platform to rapidly build and deploy the next generation of digital apps, including mobile, wearables, conversation, web, and PWAs.
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
| **{{site.data.keyword.ta}}** | A developer tool that helps you plan, prioritize, and package your on-premises workloads for modernization |
| **IBM Application Navigator** | A tool that helps you visualize, inspect, and monitor the deployed resources in applications |
| **IBM Cloud Private** | A private cloud platform that provides the benefits of the public cloud from the safety of your firewall-protected data center |

For more information about these products, see the **Key offerings** section of the [About](cloud-pak-applications?topic=cloud-pak-applications-about) page.

## Before you begin
{: #prereqs}
Before you can install the Cloud Pak, you must purchase a license. The part numbers for {{site.data.keyword.icpa_short}} are as follows. You can have one installation of {{site.data.keyword.icpa_short}} per license.

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
| IBM Applicaton Navigator | 1 | 1 | 3 |  |
| **Total** | **27** | **12** | **36** | **2** |

If you do not have a cluster, create one and then return to the {{site.data.keyword.icpa_short}} page.

Also, ensure that you have the proper IBM Cloud Identity and Access Management (IAM) permissions:

| Service or Resource | IAM Roles |
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
Ensure that an entitlement is assigned.  If not, you must get an entitlement.

Confirm your agreement to the Third-Party Service Agreements by checking the box.

Set the `consoleRoutePrefix` parameter.  This value is used as the subdomain in the URL for the {{site.data.keyword.icpa_short}} landing page; the remainder of the URL is the OpenShift Cluster Console URL.

## Step 5. Install the Cloud Pak
{: step5}
Click **Install**.

## Step 6. Next steps
{: step6}
After the installation completes, verify that you can access the dashboards.

1. Click the displayed Kabanero Enterprise dashboard URL.
2. On the Kabanero Enterprise dashboard, click **Instance**. The Kabanero Enterprise instance page provides information about your collections and, under **Tools**, has links to the Tekton dashboard and other tools such as Transformation Advisor.

You can also access the Kabanero Enterprise dashboard from an OpenShift Web Console. Go to the OpenShift Container Platform application console and click **Kabanero Enterprise** from the navigation menu.

For information about how to use Kabanero Enterprise, see the [Kabanero resources ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://kabanero.io/){: new_window}.

For information about how to use Transformation Advisor, see the [Transformation Advisor web page ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://ibm.biz/cloudta){: new_window} and [videos ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://transformationadvisor.github.io/video/){: new_window}.

## Step 7. (Optional) Install optional components
{: step7}

You can install other components to add features and functionality. See [Installing in the {{site.data.keyword.icpa_short}} Knowledge Center ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SSCSJL/install-icpa.html){: new_window} for a list of optional components and installation instructions.
