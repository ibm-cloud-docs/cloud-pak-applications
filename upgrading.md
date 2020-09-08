---

copyright:
  years: 2019, 2020
lastupdated: "2020-09-08"

keywords: updating, upgrading, Cloud Pak for Applications, Kabanero, icp, icpa, icp4a, ocp, openshift, was, mobile, runtime, container

subcollection: cloud-pak-applications

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}


# Updating your environment
{: #upgrading}

Follow the instructions on this page to update an existing installation of {{site.data.keyword.icpa_short}}.

1. Ensure that you have the IBM Cloud Identity and Access Management (IAM) permissions that are required for installation. Refer to the [Before you begin section of the Getting started page](/docs/cloud-pak-applications?topic=cloud-pak-applications-getting-started#prereqs).

2. Manually upgrade from version 4.1.1 to 4.2.1 with the [command-line interface (CLI)](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.2.x/install-upgrade.html) in the {{site.data.keyword.icpa_short}} Knowledge Center.

You must manually upgrade to 4.2.1 with the CLI. If you try to upgrade with the **Update** button in the schematics workspace, you get an error and cannot fully upgrade the product.
{: tip}

<!--
## Before you begin
{: #beforeyouupgrade}

Before starting, ensure that you have the IBM Cloud Identity and Access Management (IAM) permissions that are required for installation.  Refer to the [Before you begin section of the Getting started page](/docs/cloud-pak-applications?topic=cloud-pak-applications-prereqs).

## Step 1. Use the Schematic workspace to view your installation of {{site.data.keyword.icpa_short}}
{: ustep1}
There are two ways to view your existing installation of {{site.data.keyword.icpa_short}}.

1. Log in to cloud.ibm.com.
2. In the menu, click **Schematics**.
3. Open the workspace with the installation of {{site.data.keyword.icpa_short}}.

Optionally:

1. Log in to cloud.ibm.com.
2. Click **Catalog**.
3. Under **Offering type**, check the box for **Cloud Paks** to filter the list of offerings.
4. Select {{site.data.keyword.icpa_short}}.
5. On the **Create** tab, expand **View the existing installations**.
6. Click the link to the schematics workspace.

## Step 2. Open settings view
{: ustep2}
In the Schematics workspace, click the **Settings** view from the menu.

## Step 3. Update the installation
{: ustep3}
In the **Summary** section, the offering version that is currently installed is displayed. If an update to a newer version is available, the **Update** button is enabled.  To upgrade, select the version that you want to upgrade to and click the **Update** button.  A new plan is created that updates {{site.data.keyword.icpa_short}} in the cluster.

## After updating
{: uafter}

To view the logs, navigate to the **Activity** view from the menu, then click **View logs** on the plan that is being applied.

-->
