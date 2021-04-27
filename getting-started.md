---

copyright:
  years: 2019, 2021
lastupdated: "2021-04-27"

keywords: getting started tutorial, getting started, Cloud Pak for Applications, Kabanero, icp, icpa, icp4a, ocp, openshift, was, mobile, runtime, container

subcollection: cloud-pak-applications

content-type: tutorial
completion-time: 30m

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:term: .term}
{:external: target="_blank" .external}
{:step: data-tutorial-type='step'}


# Getting started with {{site.data.keyword.icpa_short}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="30m"}

This information applies to {{site.data.keyword.icpa_rm}} version 4.3.x on {{site.data.keyword.cloud}}. For information about version 5.1.x, see the [IBM {{site.data.keyword.icpa_short}} 5.1.x documentation](https://www.ibm.com/docs/cloud-paks/cp-applications/5.1?topic=installing){: external}.
{: note}

{{site.data.keyword.icpa_rm}} is an enterprise-ready, containerized software solution for modernizing existing applications and developing new cloud-native apps that run on {{site.data.keyword.redhat_full}} OpenShift&reg;. This hybrid, multicloud foundation breaks down technology and data silos to make modernization faster and more secure, and speeds development of applications built for Kubernetes. You can access cloud services and meet the technology standards and policies your company requires. With IBM {{site.data.keyword.mobilefoundation_short}} in this {{site.data.keyword.IBM_notm}} Cloud Pak, developers get a secured platform to rapidly build and deploy the next generation of digital apps, including mobile, wearables, conversation, web, and PWAs.
{: shortdesc}

## What's inside this {{site.data.keyword.IBM_notm}} Cloud Pak
{: #whatsinside}
{{site.data.keyword.icpa_short}} includes the following products and components:

| Product | Description |
| ------- | ----------- |
| **IBM WebSphere Application Server** | Industry-leading, production-ready, standards-based Java&trade; EE-compliant architectures |
| **IBM {{site.data.keyword.mobilefoundation_short}}** | An industry-leading, secured platform for developing and deploying the next generation of digital apps |
| **IBM Cloud Private** | A private cloud platform that provides the benefits of the public cloud from the safety of your firewall-protected data center |
| **{{site.data.keyword.redhat_notm}} {{site.data.keyword.openshiftshort}} Container Platform** |  A comprehensive solution for hybrid cloud, enterprise container, and Kubernetes development and deployments |
| **{{site.data.keyword.redhat_notm}} Runtimes** | Open runtimes, tools, and components for developing and maintaining cloud-native applications |


| Component | Description |
| ------- | ----------- |
| **{{site.data.keyword.cloud_notm}} {{site.data.keyword.ta_short}}** | A developer tool that helps you plan, prioritize, and package your on-premises workloads for modernization |
| **IBM {{site.data.keyword.ke_notm}}** [(Deprecated)](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/about-deprecations.html){: external} | A microservices-based framework that simplifies development, build, and deployment of applications for both Kubernetes and Knative (serverless). |
| **IBM {{site.data.keyword.appnav}}** [(Deprecated)](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/about-deprecations.html){: external} | A tool that helps you visualize, inspect, and monitor the deployed resources in applications |


For more information about these products, see the **Key offerings** section of the [About](/docs/cloud-pak-applications?topic=cloud-pak-applications-about) page.

## Before you begin
{: #prereqs}

Before you can install the {{site.data.keyword.IBM_notm}} Cloud Pak, you must purchase a Cloud Pak license and configure a {{site.data.keyword.redhat_notm}} {{site.data.keyword.openshiftshort}} cluster for use with the Cloud Pak.

To purchase a {{site.data.keyword.icpa_short}} license, consult your IBM representative or authorized IBM Business Partner. You can schedule a consultation from the [{{site.data.keyword.icpa}} web page](https://www.ibm.com/cloud/cloud-pak-for-applications){: external}. If your organization already purchased a valid license, your account administrator must bind the entitlement to your {{site.data.keyword.cloud_notm}} account before you can assign an entitlement with the [**Create** tab](#step1).

The part numbers for {{site.data.keyword.icpa_short}} are as follows. You can have one installation of {{site.data.keyword.icpa_short}} per license.

| Part Number | Description |
| ----------- | ----------- |
| E0QB6LL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE ANNUAL SW SUBSCRIPTION & SUPPORT RENEWAL |
| D24XKLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE SW SUBSCRIPTION & SUPPORT REINSTATEMENT 12 MONTHS |
| E0QB7LL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE FOR IBM Z ANNUAL SW SUBSCRIPTION & SUPPORT RENEWAL |
| D24XMLL | IBM CLOUD PAK FOR APPLICATIONS VIRTUAL PROCESSOR CORE FOR IBM Z SW SUBSCRIPTION & SUPPORT REINSTATEMENT 12 MONTHS |


Get a {{site.data.keyword.redhat_notm}} {{site.data.keyword.openshiftshort}} classic cluster and configure it for use with the Cloud Pak. If you do not have a cluster, [create a classic {{site.data.keyword.openshiftshort}} cluster](/docs/openshift?topic=openshift-getting-started#clusters_gs) and then return to the {{site.data.keyword.icpa_short}} page.

Make sure that the cluster meets the minimum scheduling capacity:

| Software | Nodes | Memory (GB/node) | CPU (cores/node) | Disk (GB/node) |
| --- | --- | --- | --- | --- |
| {{site.data.keyword.ke}}, {{site.data.keyword.ta_short}}, and {{site.data.keyword.appnav}} | 3 | 16 | 4 | 20 |
| {{site.data.keyword.ke}}, {{site.data.keyword.ta_short}}, {{site.data.keyword.appnav}}, and {{site.data.keyword.mobilefoundation_short}} | 5 | 16 | 4 | 20 |
| CodeReady Workspaces with Codewind workspace (add 1 node per 8 developers) | 1 | 16 | 4 | 20 |

To determine the amount of scheduling capacity you need, consider several things. First, the size of the core capabilities that you are deploying, the optional capabilities you want to use, and the capacity for your applications. Second, consider how {{site.data.keyword.redhat_notm}} {{site.data.keyword.openshiftshort}} updates are scheduled and allow adequate capacity for a failure. The amount of capacity must allow for the spike in CPU as the runtimes initialize and their steady state use. The table shows the recommended capacity for a minimal environment to try the Cloud Pak. It assumes a building block of each worker node has 4 CPUs, 16 GB Memory, and 20 GB Disk on each block. The capacity allows a single worker node at a time to be quiesced, updated, and reactivated into the cluster, and allows the environment to remain operational. It is best to always have a single node capacity available for high availability.
{: tip}

Additional resources are required if the {{site.data.keyword.cloud_notm}} Platform Common Services are installed. For more information, see [Common Services prerequisites](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/install-prerequisites-cs.html){: external}.


Also, ensure that you have the proper {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) permissions:

| Service or Resource | IAM Roles |
| ----------------- | ------------------- |
| 'Kubernetes Cluster' service | Manager and Writer |
| Resource Group containing the OCP cluster | Viewer |
| 'License and Entitlement' service | Editor |
| 'Schematics' service | Manager |

For more information on IAM roles and permissions, see [IAM access](/docs/account?topic=account-userroles).

{{site.data.keyword.icpa_short}} has been tested with the File Gold and Block Gold {{site.data.keyword.cloud_notm}} storage options.


## Configure your installation environment
{: #step1}
{: step}

On the [Cloud Pak **Create** tab](https://cloud.ibm.com/catalog/content/ibm-cp-applications) in the {{site.data.keyword.cloud_notm}} catalog, select a target cluster, and then select or type a name for your project in the **Project** field.

You can view existing installations of {{site.data.keyword.icpa_short}} by expanding **View existing installations**.

## Configure your workspace
{: #step2}
{: step}

Define how your installation is managed in a Schematics workspace.

You can type a name for the installation in the **Name** field, or use the default. To view your existing resources,
see the [resource list page](https://cloud.ibm.com/resources).

Select a resource group from the **Resource group** list, or use the default. For more information on resource
groups, see [Best practices for organizing resources and assigning access](/docs/account?topic=account-account_setup).

Enter any tags that you want to use to organize this resource in the **Tags** field in a comma-separated list. Tags can
contain special characters, which can be used in creating key-value pairs such as `key:value` for grouping related tags. Tags are visible across the account.

## Complete the pre-installation
{: #step3}
{: step}

Run the preinstallation script. Only a cluster administrator can run the script. If you do not have the proper role on the cluster, click **Share link** to share the preinstallation script with your cluster administrator. Otherwise, click **Run script** to execute the script. Confirm that the script completed successfully.

## Set the deployment values
{: #step4}
{: step}

Set the `consoleRoutePrefix` parameter. This value is used as the subdomain in the URL for the {{site.data.keyword.icpa_short}} landing page. The remainder of the URL is the {{site.data.keyword.openshiftshort}} Cluster Console URL.

Expand **Parameters with default values** and change the values as needed. To install {{site.data.keyword.mobilefoundation_short}}, set `mobileFoundation` to `true` and specify values for the `mobileFoundation*` deployment parameters. To install Common Services, set `commonServices` to `true` and review the values for the remaining `commonServices*` deployment parameters.

If you are installing {{site.data.keyword.mobilefoundation_short}} and use SSL with a DB2 database, you must [install {{site.data.keyword.mobilefoundation_short}} with the {{site.data.keyword.IBM_notm}} Cloud Pak CLI](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/install-mf-cli.html){: external}. You cannot set SSL options in the {{site.data.keyword.cloud_notm}} catalog if you use a DB2 database that runs on SSL. You can [set SSL options in {{site.data.keyword.mobilefoundation_short}} installations](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/install-mf-cli.html#install-steps-mf){: external} with the CLI (see step 1, substep 3).
{: important}

## Install the Cloud Pak
{: #step5}
{: step}

Ensure that an entitlement is assigned. If not, you must get an entitlement.

Confirm your agreement to the Third-Party Service Agreements by checking the box. Then, click **Install**.

## Access the dashboards
{: #step6}
{: step}

After the installation completes, verify that you can access the dashboards.

1. Click the workspace name: **Schematics / Workspace / *workspace_name* **
2. On the workspace activity page, click **Offering dashboard**.

To view the Cloud Pak instance page, click ![Console hamburger menu icon](images/hamburger_icon.png) **&gt; Instance** or click the **View team instance** button. The instance page provides information about your stacks and has links to the Tekton dashboard and other tools such as {{site.data.keyword.ta_short}} and {{site.data.keyword.appnav}}.
{: tip}

You can also access the dashboard from an {{site.data.keyword.openshiftshort}} Web Console. Go to the {{site.data.keyword.openshiftshort}} Container Platform application console and click **Cloud Pak Console** from the navigation menu.

For information about how to use {{site.data.keyword.ke_notm}}, see the [documentation about developing, building, deploying, and managing applications](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x){: external}.

For information about how to use {{site.data.keyword.ta_short}}, see the {{site.data.keyword.ta_short}} [documentation](https://www.ibm.com/support/knowledgecenter/SS5Q6W){: external}, [videos](https://transformationadvisor.github.io/video/){: external}, and [web page](https://ibm.biz/cloudta){: external}.

For information about how to use {{site.data.keyword.appnav}}, see [Managing the environment](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/admin-overview.html){: external} in the {{site.data.keyword.icpa_short}} documentation or the [{{site.data.keyword.appnav}} web page](https://ibm.github.io/appnav){: external}.

## (Optional) Install optional components
{: #step7}
{: step}

You can install other products to which you're entitled. See [Installing](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.3.x/install-icpa.html){: external} for a list of optional components and installation instructions.
