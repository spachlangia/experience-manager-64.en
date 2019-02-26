---
title: Storage Configuration
seo-title: Storage Configuration
description: How to access the Storage Configuration Console
seo-description: How to access the Storage Configuration Console
uuid: b5f7c17b-ad63-430c-9f9d-baa1462a119e
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 4df3e400-ac95-4cd2-9bbf-2b003724c071
---

# Storage Configuration{#storage-configuration}

Storage configuration is the means of identifying the storage chosen for community content, also known as user generated content (UGC).

This setting informs the AEM Communities code as to which implementation of the storage resource provider (SRP) is to be used when accessing UGC and must reflect the topology established when AEM was deployed.

For a discussion of storage options and deployment topologies, visit

* [Community Content Store](../../communities/using/working-with-srp.md)
* [Recommended Topologies](../../communities/using/topologies.md)

## Storage Configuration Console {#storage-configuration-console}

![](assets/chlimage_1-188.png)

In the author environment, to reach the storage configuration console

* from global navigation : **Tools, Communities, Storage Configuration**

To select a storage option other than the default JCR :

* select an option
* configure appropriately

    * see details for [selecting MSRP](../../communities/using/msrp.md#selectmsrp)
    * see details for [selecting DSRP](../../communities/using/dsrp.md#selectdsrp)
    * see details for [selecting ASRP](../../communities/using/asrp.md#selectasrp)

* select **Submit**

### About JCR Storage {#about-jcr-storage}

Be aware that if no selection is made, the default is the AEM repository, JCR.

JCR is *not *a common store shared by the author and publish environments. Community content will be visible only from the author or publish environment in which it was created.

Visit [JCR Store](../../communities/using/jsrp.md) for additional information.

>[!NOTE]
>
>The absence of the node `srpc`under `/etc/socialconfig` indicates the default [JCR store](../../communities/using/jsrp.md).
