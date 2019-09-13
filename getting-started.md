---

copyright:
  years: 2019
lastupdated: "2019-09-06"

keywords: getting started tutorial, getting started, Cloud Pak for Applications, Kabanero

subcollection: cloud-pak-applications

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}


<!-- Please delete content examples and coding that you are not using for your service. -->

# Getting started with IBM Cloud Pak for Applications
{: #getting-started}

<!-- The title of your H1 should be Getting started with _cloud-pak_, where _cloud-pak_ is the
non-trademarked short version conref. Include getting started and variations of your cloud pak
name and function in the `meta keywords` values. See the example keywords above. -->

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a user would want to use this Cloud Pak.
Briefly mention what the user's learning goal is and include the following SEO keywords in the title and/or the short description: IBM Cloud, CloudPakName. Be sure to use conversational style. For more details, see the guidance on conversational style in the Carbon Design System at http://www.carbondesignsystem.com/guidelines/content/general.

Example: -->

IBM Cloud Pak for Applications is an enterprise-ready, containerized software solution for modernizing existing applications and developing new cloud-native apps that run on Red Hat OpenShift. This hybrid, multicloud foundation breaks down technology and data silos to make modernization faster and more secure, and speeds development of applications built for Kubernetes, so you can access cloud services — all while meeting the technology standards and policies your company requires.
{: shortdesc}

<!-- Component section: REQUIRED
The component section includes a list of the offerings included in the Cloud Pak. Also include where a user can find more information on each offering.

Example: -->

## What's inside this Cloud Pak
{: #whatsinside}
IBM Cloud Pak for Applications includes the following products.

### IBM WebSphere Application Server
{: was}
WebSphere Application Server, with its traditional and Liberty runtimes, offers industry-leading, production-ready, standards-based Java™ EE compliant architectures. Cloud Pak for Applications include WebSphere Application Server ND, WebSphere Application Server, and the WebSphere Liberty Core editions with the ability to easily mix and match between them.

### Red Hat OpenShift Container Platform
{: ocp}
Red Hat OpenShift delivers a comprehensive solution for hybrid cloud, enterprise container, and Kubernetes development and deployments. It includes an enterprise-grade Linux® operating system, container runtime, networking, monitoring, container registry, authentication, and authorization solutions.

### Kabanero Enterprise
{: kabent}
Kabanero Enterprise is the commercial enterprise-ready and fully supported implementation of the Kabanero.io open source community project. Kabanero Enterprise integrates with, extends, and adds value to Red Hat OpenShift.  The Kabanero open source project is focused on bringing together foundational open source technologies into a modern microservices-based framework.

Learn more about Kabanero at the [Kabanero.io website](https://kabanero.io).

### Red Hat Runtimes
{: rhrt}
Red Hat Runtimes provides a set of open runtimes, tools, and components for developing and maintaining cloud-native applications. It offers lightweight runtimes and frameworks for highly distributed cloud architectures, such as microservices.

### IBM Mobile Foundation
{: mobile}
IBM Mobile Foundation offers an industry-leading secured platform for developers to rapidly build and deploy the next generation of digital apps, including mobile, wearables, conversation, web, and PWAs. With Mobile Foundation, developers get containerized mobile back-end services covering comprehensive security, application life cycle management, push notifications, feature toggle, off-line sync, and back-end integration.


<!-- Task section: REQUIRED
The task section includes steps to get the Cloud Pak installed through IBM Cloud and next initial steps to get up and running.
- DO include the basic, most-common-use scenario steps to use the Cloud Pak.
- DO NOT repeat the UI from IBM Cloud catalog details page; instead, reference the pages or sections.
-->

<!-- Include a prerequisites paragraph for any prerequisites to be met. For example: REQUIRED -->
## Before you begin
{: #prereqs}
Before you can install the Cloud Pak, you must purchase a license through
[IBM Passport Advantage  ![External link icon](../../icons/launch-glyph.svg "External link icon")]](https://www.ibm.com/software/passportadvantage/index.html){:new_window}.
The part number for IBM Cloud Pak for Applications is D22H2LL.  You can have one installation of {{site.data.keyword.icpa_short}} per license.

Make sure you have a RedHat OpenShift cluster already set up and that it meets the minimum requirements: ___ . If you have not already set up a cluster, create one and then return to the {{site.data.keyword.icpa_short}} page.

## Step 1. Configure your installation environment
{: step1}
Select a target cluster, and then select or type a name for your project in the **Project** field.

You can view existing installations of {{site.data.keyword.icpa_short}} by expanding **View existing installations**.

## Step 2. Configure your workspace
{: step2}
In this step you will define how your installation will be managed in a Schematics workspace.

You can type a name for the installation in the **Name** field, or use the default.  To view your existing resources,
see the [resource list page](https://test.cloud.ibm.com/resources).

Select a resource group from the **Resources** drop-down list or use the default.  For more information on resource
groups, see [Best practices for organizing resources in a resource group](https://test.cloud.ibm.com/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).

Enter any tags you want to use to organize this resource in the **Tags** field in a comma-separated list.  Tags can
contain special characters, which can be used in creating key-value pairs (e.g., key:value) for grouping related tags.  
Note that tags are visible across the account.

## Step 3. Complete the pre-installation
{: step3}
Click **Run script**.  If you do not have the proper role on the cluster, you will need to have someone with the proper
authority run this script.  A sample preinstallation script with default values is shown:
```
#!/bin/sh

oc adm policy add-scc-to-user anyuid system:serviceaccount:${JOB_NAMESPACE}:default
oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:${JOB_NAMESPACE}:default
oc adm policy add-cluster-role-to-user self-provisioner system:serviceaccount:${JOB_NAMESPACE}:default

echo "SCRIPT RAN SUCCESSFULLY"
```
{: screen}

Confirm that the script completed successfully.

## Step 4. Set the deployment values
{: step4}
Enter your entitlement information that you received from IBM Passport Advantage.

Confirm that you have read and agree to the Third-Party Service Agreements by checking the box.

## Step 5. Install the cloud pak
{: step5}
Click **Install**.

## Step 6. Next steps
{: step6}
Once the installation has completed, links to your IBM Cloud Paks for Applications landing page, your Tekton Dashboard, and your Transformation Advisor UI are provided.  You can click the **View log** link and find them at the bottom of the log file, or through the UI:

1. Login to the Openshift console.
1. Click **Service Catalog**, then select **Application Console**.  You should see several projects installed.
   - If you click the **kabanero** project, the Overview tab contains the URLs to the **icpa-landing** page and the **tekton-dashboard**.
   - If you click the **ta** project, the Overview tab contains the URL to the Transformation Advisor UI.


<!-- For code examples:
- use three backticks ahead of and after the example (```)
- For copyable code snippet, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in framework in output.
- For copyable command, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.
- For non-copyable output snippet, include {: screen} following the last set of backticks.
 -->

<!--
	```
	Copyable example for this step.
	This example might be multiline code
	to copy into a file.
	When displayed in the doc framework,
	it will have a copy button on the right.
	The user can click to copy the example
	so they can paste it into their code editor.
	```
	{: codeblock}

	```
	This is a bunch of output from
		a command or program I ran
			and it can run lots of lines
			and the doc framework will show it as
			output with no copy button.
	```
	{: screen}


## Next steps -->

<!-- Add the topic to your `toc` file:


{:navgroup: .navgroup}
{:topicgroup: .topicgroup}

{: .toc subcollection="<Folder_name>" audience="<category>" href="/docs/<folder_name>?topic=<subcollection>getting-started"}
<Cloud Pak Name>

    {: .navgroup id="learn"}
    getting-started.md

    {: .topicgroup}
    Related links
        [Link text](link URL)
    {: .navgroup-end}

    {: .navgroup id="reference"}
    Reference
    [Link text](link URL)
    {: .navgroup-end}
-->
