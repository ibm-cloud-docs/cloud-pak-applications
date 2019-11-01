---

copyright:
  years: 2019
lastupdated: "2019-11-1"

subcollection: cloud-pak-applications
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}

# Troubleshooting
{: #troubleshooting}

You might encounter an issue when installing or otherwise using the Cloud Pak.

To diagnose problems with the installer, first view the log files. If the log files do not identify the problem, see the following information.

The issues listed on this page are specific to installing and running {{site.data.keyword.icpa_short}} on IBM Cloud.  For the complete list of troubleshooting issues, see the [Troubleshooting page for {{site.data.keyword.icpa_short}} in the Knowledge Center](https://www.ibm.com/support/knowledgecenter/SSCSJL/troubleshoot.html).

## Installation stops due to timeout error
{: #timeout}

During peak hours, popular datacenters might experience higher than usual traffic. This can occasionally cause a drop in connection in the Cloud Pak for Applications installer. You can simply re-run the installer if the installation fails with a message like the following:

```
2019/09/19 21:22:53 Terraform apply | Unable to connect to the server: net/http: TLS handshake timeout
```


To re-run the installer, go to the `Activity` tab in the schematics workspace and click `Apply Plan`.

## 'docker push' fails with gateway time-out error
{: #pushtimeout}

Performing a `docker push` into an internal Docker registry might result in the following error:

```
received unexpected HTTP status: 504 Gateway Time-out
```

This occurs because the input-output operations per second (IOPS) setting for the backing storage of the registry's persistent volume (PV) is too low.

To resolve this problem, change the IOPS setting of the PV's backing storage device. Refer to [Changing the size and IOPS of your existing storage device](https://cloud.ibm.com/docs/openshift?topic=openshift-file_storage#file_change_storage_configuration) for instructions and additional information.

Note that changing the storage tier is one way to achieve a higher IOPS setting, and you can also increase the size of the backing storage by doing so.
