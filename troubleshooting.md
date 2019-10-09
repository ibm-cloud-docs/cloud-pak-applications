---

copyright:
  years: 2019
lastupdated: "2019-10-09"

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


## Installation stops due to timeout error
{: #timeout}

During peak hours, popular datacenters may experience higher than usual traffic. This can occasionally cause a drop in connection in the Cloud Pak for Applications installer. You can simply re-run the installer if the installation fails with a message like the following:

```
2019/09/19 21:22:53 Terraform apply | Unable to connect to the server: net/http: TLS handshake timeout
```


To re-run the installer, go to the `Activity` tab in the schematics workspace and click `Apply Plan`.
