---
title: JSRP - JCR Storage Resource Provider
seo-title: JSRP - JCR Storage Resource Provider
description: JSRP is generally best suited for demonstration or development environments of one publish instance and one author instance
seo-description: JSRP is generally best suited for demonstration or development environments of one publish instance and one author instance
uuid: e80df7bd-e2f4-445a-8e8a-2f94d15ce507
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: fb7f5442-0d57-472a-bf44-17730464bfc6
---

# JSRP - JCR Storage Resource Provider{#jsrp-jcr-storage-resource-provider}

## About JSRP {#about-jsrp}

When AEM Communities uses JSRP as its storage option (the default), community content is stored in JCR and user generated content (UGC) is accessible only from the author or publish instance to which it was posted.

Because of the simplicity of deployment, JSRP is generally best suited for demonstration or development environments of one publish instance and one author instance.

See also [Characteristics of SRP Options](../../communities/using/working-with-srp.md#characteristicsofsrpoptions) and [Recommended Topologies](../../communities/using/topologies.md).

## Configuration {#configuration}

### Select JSRP {#select-jsrp}

By default, JSRP is the storage option for UGC.

The [Storage Configuration console](../../communities/using/srp-config.md) allows for the selection of the default storage configuration, which identifies which implementation of SRP to use.

In the author environment, to reach the Storage Configuration console

* from global navigation : **Tools, Communities, Storage Configuration**

![](assets/chlimage_1-234.png)

* select **JCR Storage Resource Provider (JSRP)**
* select **Submit**

### Publishing the Configuration {#publishing-the-configuration}

While JSRP is the default configuration, to ensure the identical configuration is set in the publish environment :

* on author :

    * from global navigation : **Tools, Deployment, Replication**
    * select **Activate Tree**
    * **Start Path :**

        * browse to `/etc/socialconfig/srpc/`

    * select **Activate**

## Managing User Data {#managing-user-data}

For information regarding *users*, *user profiles* and *user groups*, often entered in the publish environment, visit

* [User Synchronization](../../communities/using/sync.md)
* [Managing Users and User Groups](../../communities/using/users.md)

## Troubleshooting {#troubleshooting}

### UGC Not Visible in JCR {#ugc-not-visible-in-jcr}

Make sure JSRP has been configured to be the default provider by checking the configuration of the storage option. By default, the storage resource provider is JSRP.

On all author and publish AEM instances, revisit the Storage Configuration console or check the AEM repository :

* in JCR, if [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

    * does not contain an [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) node, it means the storage provider is JSRP
    * if the srpc node exists and contains node [defaultconfiguration](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration), the defaultconfiguration's properties should define JSRP to be the default provider

### UGC Not Visible on Author Instance {#ugc-not-visible-on-author-instance}

This is not a bug. A characteristic of JSRP is that community content entered in the publish environment will only be visible in the publish environment.

### UGC Not Visible on Publish Instance {#ugc-not-visible-on-publish-instance}

If a single publish instance or if a publish cluster is deployed, then follow instructions for [UGC Not Visible in JCR](#ugcnotvisibleinjcr).

If a publish farm is deployed, a characteristic of JSRP is that community content will only be visible on the publish instance to which it was posted.

For UGC to be visible from any publish instance, a publish cluster is required.