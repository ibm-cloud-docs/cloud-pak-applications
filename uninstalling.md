---

copyright:
  years: 2020
lastupdated: "2020-04-30"

keywords: uninstalling, removing, Cloud Pak for Applications, workspace, resource

subcollection: cloud-pak-applications

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:external: target="_blank" .external}


# Uninstalling your workspace or resources
{: #uninstalling}

You can uninstall the {{site.data.keyword.icpa_short}} workspace or resources from the Schematics workspace for your Cloud Pak installation.
{: shortdesc}

## Before you begin
{: #beforeyouuninstall}

Ensure that you have the IBM Cloud Identity and Access Management (IAM) permissions that are required for installation. Refer to the [Before you begin](/docs/cloud-pak-applications?topic=cloud-pak-applications-getting-started#prereqs) section of the Getting started page.

## Step 1. Use the Schematic workspace to view your installation of {{site.data.keyword.icpa_short}}
{: #untep1}

You can view your existing installation of {{site.data.keyword.icpa_short}} in two ways.

1. Log in to cloud.ibm.com.
2. In the menu, click **Schematics**.
3. Open the workspace with the installation of {{site.data.keyword.icpa_short}}.
<br/>

Or:

1. Log in to cloud.ibm.com.
2. Click **Catalog**.
3. Under **Software**, check the box for **Cloud Paks** to filter the list of offerings.
4. Select {{site.data.keyword.icpa_short}}.
5. On the **Create** tab, expand **View the existing installations**.
6. Click the link to the Schematics workspace.

## Step 2. Delete resources and, optionally, the workspace
{: #unstep2}

1. From the Schematics workspace for your Cloud Pak installation, click **Actions &gt; Delete**.
2. In the Delete workspace dialog, select **Delete all associated resources** and, optionally, **Delete workspace**.

If you select to delete the workspace without also selecting to delete all associated resources, the resources remain on your cluster. To uninstall the resources, you must use the [Cloud Pak CLI](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x/install-uninstall.html){: external}.
{: important}


## After uninstalling
{: #unafter}

To view the logs, go to the **Activity** view from the menu, then click **View logs** on the uninstallation action.
