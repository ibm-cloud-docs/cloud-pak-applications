---

copyright:
  years: 2019, 2020
lastupdated: "2020-08-24"

subcollection: cloud-pak-applications
---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:external: target="_blank" .external}


# Troubleshooting
{: #troubleshooting}

You might encounter an issue when installing or otherwise using the Cloud Pak.

To diagnose problems with the installer, first view the log files. If the log files do not identify the problem, see the following information.

The issues listed on this page are specific to installing and running {{site.data.keyword.icpa_short}} on IBM Cloud. For the complete list of troubleshooting issues, see the [Troubleshooting page for {{site.data.keyword.icpa_short}} in the Knowledge Center](https://www.ibm.com/support/knowledgecenter/SSCSJL_4.2.x/troubleshoot.html).

## Installation stops due to timeout error
{: #timeout}

During peak hours, popular datacenters might experience higher than usual traffic. This can occasionally cause a drop in connection in the {{site.data.keyword.icpa_short}} installer. Rerun the installer if the installation fails with a message like the following:

```
2019/09/19 21:22:53 Terraform apply | Unable to connect to the server: net/http: TLS handshake timeout
```

To rerun the installer, go to the `Activity` tab in the schematics workspace and click `Apply Plan`.

## 'docker push' fails with gateway timeout error
{: #pushtimeout}

Performing a `docker push` into an internal Docker registry might result in the following error:

```
received unexpected HTTP status: 504 Gateway Time-out
```

This error occurs because the input/output operations per second (IOPS) setting for the backing storage of the registry's persistent volume (PV) is too low.

To resolve this problem, change the IOPS setting of the PV's backing storage device. Refer to [Changing the size and IOPS of your existing storage device](/docs/openshift?topic=openshift-file_storage#file_change_storage_configuration) for instructions and additional information.

Changing the storage tier is one way to achieve a higher IOPS setting, and you can also increase the size of the backing storage by doing so.
