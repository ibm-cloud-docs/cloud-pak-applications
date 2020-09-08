---

copyright:
  years: 2019, 2020
lastupdated: "2020-08-24"

keywords: what, new, Cloud Pak for Applications, Kabanero, icp, icpa, icp4a, ocp, openshift, was, mobile, runtime, container

subcollection: cloud-pak-applications

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Latest updates
{: #whatsnew}

Learn about new features, improvements, any limitations, and other changes in the latest product release.
{: shortdesc}

## {{site.data.keyword.icpa_short}} Version 4.2
{: #cloud-version-42}

### Version 4.2.1

* **Software support**
    * Requires [Red Hat&reg; OpenShift&reg; Container Platform (OCP) version 4.4](/docs/openshift?topic=openshift-getting-started). You cannot use {{site.data.keyword.icpa_rm}} version 4.2.1 with earlier versions of OCP.
    * Requires a [**classic** OpenShift cluster](/docs/openshift?topic=openshift-getting-started#clusters_gs).


* **Features and enhancements**
    * Removed Version 4.1.1 from the {{site.data.keyword.cloud_notm}} catalog.
    * Integrated miscellaneous service maintenance.


## {{site.data.keyword.icpa_short}} Version 4.1
{: #cloud-version-41}

### Version 4.1.1

* **Software support**
    * Requires [Red Hat OpenShift Container Platform (OCP) version 4.3](/docs/openshift?topic=openshift-getting-started) or later. You cannot use {{site.data.keyword.icpa_short}} version 4.1.1 with earlier versions of OCP.
    * Adds support for [IBM {{site.data.keyword.mobilefoundation_short}}](https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/8.0/ibmcloudpakforapplications/){: external}.
    * Adds support for [IBM Cloud Platform Common Services](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x/using-cs.html){: external}.


* **Features and enhancements**
    * Changed the name of the _IBM Kabanero&trade; Enterprise_ software offering to _Accelerators for Teams_. Learn about {{site.data.keyword.ke_notm}} in the documentation about developing, building, deploying, and managing applications in the [{{site.data.keyword.icpa_short}} Knowledge Center](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.1.x){: external}.
    * Removed Version 3.0.1 from the {{site.data.keyword.cloud_notm}} catalog.
    * Removed instructions for upgrading because you cannot upgrade directly from Version 3.0 to Version 4.1.
    * Added instructions for [uninstalling](/docs/cloud-pak-applications?topic=cloud-pak-applications-uninstalling) your Cloud Pak workspace and resources.
    * Integrated miscellaneous service maintenance.


## {{site.data.keyword.icpa_short}} Version 3.0
{: #cloud-version}

### Version 3.0.1

* **Software support**
    * Adds support for [IBM Application Navigator](https://github.com/IBM/appnav){: external}


* **Features and enhancements**
    * Added instructions for upgrading
    * Added the `setup-collections` and `build-collections` commands to add {{site.data.keyword.ke_notm}} collections to your GitHub Enterprise instance and to build the collections
    * Added the `kabanero.github.teams` setting to the `config.yaml` configuration file to specify teams in your GitHub Enterprise organization for the `setup-collections` command
    * Added the **Docs** and **Guides** tabs to the {{site.data.keyword.ke_notm}} dashboard, for easy access to {{site.data.keyword.ke_notm}} documentation


### Version 3.0.0

* **Software support**
    * Adds support for Red Hat OpenShift Container Platform
    * Adds support for {{site.data.keyword.ke_notm}}
    * Adds support for {{site.data.keyword.ta_short}}
    * Adds support for Red Hat Runtimes
    * Adds support for Developer tools (Eclipse Codewind)
    * Adds support for IBM Mobile Foundation


* **Features and enhancements**
    * Added [instructions](/docs/cloud-pak-applications?topic=cloud-pak-applications-getting-started) for installing {{site.data.keyword.icpa_short}}
