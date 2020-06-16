---

copyright:
  years: 2019, 2020
lastupdated: "2020-06-09"

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

{{site.data.keyword.icpa_rm}} is an enterprise-ready, containerized software solution for modernizing existing applications and developing new cloud-native apps that run on Red Hat&reg; OpenShift&reg;. This hybrid, multicloud foundation breaks down technology and data silos to make modernization faster and more secure, and speeds development of applications built for Kubernetes. You can access cloud services and meet the technology standards and policies your company requires. With IBM {{site.data.keyword.mobilefoundation_short}} in this Cloud Pak, developers get a secured platform to rapidly build and deploy the next generation of digital apps, including mobile, wearables, conversation, web, and PWAs.
{: shortdesc}

## What's inside this Cloud Pak
{: #whatsinside}
{{site.data.keyword.icpa_short}} includes the following products:

| Product | Description |
| ------- | ----------- |
| **IBM WebSphere Application Server** | Industry-leading, production-ready, standards-based Java&trade; EE-compliant architectures |
| **Red Hat OpenShift Container Platform** |  A comprehensive solution for hybrid cloud, enterprise container, and Kubernetes development and deployments |
| **{{site.data.keyword.ke}}** | The commercial, enterprise-ready, and fully supported implementation of the Kabanero.io open source community project |
| **Red Hat Runtimes** | Open runtimes, tools, and components for developing and maintaining cloud-native applications |
| **IBM {{site.data.keyword.mobilefoundation_short}}** | An industry-leading, secured platform for developing and deploying the next generation of digital apps |
| **IBM Modernization &amp; Developer Tools** | Tools to assist with your move to the cloud |
| **{{site.data.keyword.cloud_notm}} {{site.data.keyword.ta_short}}** | A developer tool that helps you plan, prioritize, and package your on-premises workloads for modernization |
| **IBM {{site.data.keyword.appnav}}** | A tool that helps you visualize, inspect, and monitor the deployed resources in applications |
| **IBM Cloud Private** | A private cloud platform that provides the benefits of the public cloud from the safety of your firewall-protected data center |

For more information about these products, see the **Key offerings** section of the [About](/docs/cloud-pak-applications?topic=cloud-pak-applications-about) page.

## Before you begin
{: #prereqs}

Before you can install the Cloud Pak, you must purchase a Cloud Pak license and configure a Red Hat OpenShift cluster for use with the Cloud Pak.

To purchase a {{site.data.keyword.icpa_short}} license, consult your IBM representative or authorized IBM Business Partner. You can schedule a consultation from the [{{site.data.keyword.icpa}} web page](https://www.ibm.com/cloud/cloud-pak-for-applications){: external}. If your organization already purchased a valid license, your account administrator must bind the entitlement to your {{site.data.keyword.cloud_notm}} account before you can assign an entitlement with the [**Create** tab](#step1).

The part numbers for {{site.data.keyword.icpa_short}} are as follows. You can have one installation of {{site.data.keyword.icpa_short}} per license.

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

Get a Red Hat OpenShift cluster and configure it for use with the Cloud Pak. If you do not have a cluster, create one and then return to the {{site.data.keyword.icpa_short}} page.

Make sure that the cluster meets the minimum scheduling capacity:

| Software | Nodes | Memory (GB/node) | CPU (cores/node) | Disk (GB/node) |
| --- | --- | --- | --- | --- |
| {{site.data.keyword.ke}}, {{site.data.keyword.ta_short}}, and {{site.data.keyword.appnav}} | 3 | 16 | 4 | 20 |
| {{site.data.keyword.ke}}, {{site.data.keyword.ta_short}}, {{site.data.keyword.appnav}}, and {{site.data.keyword.mobilefoundation_short}} | 5 | 16 | 4 | 20 |
| CodeReady Workspaces with Codewind workspace (add 1 node per 8 developers) | 1 | 16 | 4 | 20 |

To determine the amount of scheduling capacity you need, consider several things. First, the size of the core capabilities that you are deploying, the optional capabilities you want to use, and the capacity for your applications. Second, consider how Red Hat OpenShift updates are scheduled and allow adequate capacity for a failure. The amount of capacity must allow for the spike in CPU as the runtimes initialize and their steady state use. The table shows the recommended capacity for a minimal environment to try the Cloud Pak. It assumes a building block of each worker node has 4 CPUs, 16 GB Memory, and 20 GB Disk on each block. The capacity allows a single worker node at a time to be quiesced, updated, and reactivated into the cluster, and allows the environment to remain operational. It is best to always have a single node capacity available for high availability.
{: tip}

Additional resources are required if the IBM Cloud Platform Common Services are installed. For more information, see [Common Services prerequisites](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x/install-prerequisites-cs.html){: external}.


Also, ensure that you have the proper IBM Cloud Identity and Access Management (IAM) permissions:

| Service or Resource | IAM Roles |
| ----------------- | ------------------- |
| 'Kubernetes Cluster' service | Manager and Writer |
| Resource Group containing the OCP cluster | Viewer |
| 'License and Entitlement' service | Editor |
| 'Schematics' service | Manager |

For more information on IAM roles and permissions, see [Managing identity and access](/docs/iam?topic=iam-userroles).

## Step 1. Configure your installation environment
{: #step1}

On the [Cloud Pak **Create** tab](https://cloud.ibm.com/catalog/content/ibm-cp-applications) in the {{site.data.keyword.cloud_notm}} catalog, select a target cluster, and then select or type a name for your project in the **Project** field.

You can view existing installations of {{site.data.keyword.icpa_short}} by expanding **View existing installations**.

## Step 2. Configure your workspace
{: #step2}
In this step, define how your installation is managed in a Schematics workspace.

You can type a name for the installation in the **Name** field, or use the default. To view your existing resources,
see the [resource list page](https://cloud.ibm.com/resources).

Select a resource group from the **Resource group** list, or use the default. For more information on resource
groups, see [Best practices for organizing resources in a resource group](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).

Enter any tags that you want to use to organize this resource in the **Tags** field in a comma-separated list. Tags can
contain special characters, which can be used in creating key-value pairs such as `key:value` for grouping related tags. Tags are visible across the account.

## Step 3. Complete the pre-installation
{: #step3}

Run the preinstallation script. Only a cluster administrator can run the script. If you do not have the proper role on the cluster, click **Share link** to share the preinstallation script with your cluster administrator. Otherwise, click **Run script** to execute the script. Confirm that the script completed successfully.

## Step 4. Set the deployment values
{: #step4}

Set the `consoleRoutePrefix` parameter. This value is used as the subdomain in the URL for the {{site.data.keyword.icpa_short}} landing page. The remainder of the URL is the OpenShift Cluster Console URL.

Expand **Parameters with default values** and change the values as needed. To install {{site.data.keyword.mobilefoundation_short}}, set `mobileFoundation` to `true` and specify values for the `mobileFoundation*` deployment parameters. To install Common Services, set `commonServices` to `true` and review the values for the remaining `commonServices*` deployment parameters.


## Step 5. Install the Cloud Pak
{: #step5}

Ensure that an entitlement is assigned. If not, you must get an entitlement.

Confirm your agreement to the Third-Party Service Agreements by checking the box. Then, click **Install**.

## Step 6. Next steps
{: #step6}
After the installation completes, verify that you can access the dashboards.

1. Click the workspace name: **Schematics / Workspace / *workspace_name* **
2. On the workspace activity page, click **Offering dashboard**.

To view the Cloud Pak instance page, click ![Console hamburger menu icon](images/hamburger_icon.png) **&gt; Instance** or click the **View team instance** button. The instance page provides information about your stacks and has links to the Tekton dashboard and other tools such as {{site.data.keyword.ta_short}} and {{site.data.keyword.appnav}}.
{: tip}

You can also access the dashboard from an OpenShift Web Console. Go to the OpenShift Container Platform application console and click **Cloud Pak Console** from the navigation menu.

For information about how to use {{site.data.keyword.ke_notm}}, see the documentation about developing, building, deploying, and managing applications in the [{{site.data.keyword.icpa_short}} Knowledge Center](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x){: external} and the [Kabanero resources](https://kabanero.io/){: external}.

For information about how to use {{site.data.keyword.ta_short}}, see the {{site.data.keyword.ta_short}} [Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS5Q6W){: external}, [videos ](https://transformationadvisor.github.io/video/){: external}, and [web page](https://ibm.biz/cloudta){: external}.

For information about how to use {{site.data.keyword.appnav}}, see [Managing the environment](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x/admin-overview.html){: external} in the {{site.data.keyword.icpa_short}} Knowledge Center or the [{{site.data.keyword.appnav}} web page](https://ibm.github.io/appnav){: external}.

## Step 7. (Optional) Install optional components
{: #step7}

You can install other products to which you're entitled. See [Installing](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x/install-icpa.html){: external} in the {{site.data.keyword.icpa_short}} Knowledge Center for a list of optional components and installation instructions.
