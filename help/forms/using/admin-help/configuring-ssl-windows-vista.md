---
title: Configuring SSL on Windows Vista
seo-title: Configuring SSL on Windows Vista
description: Learn how to configure SSL on Windows Vista.
seo-description: Learn how to configure SSL on Windows Vista.
uuid: 20bfcefb-ec84-4c55-bceb-6af106d883d7
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 667645a0-53d0-4f9b-a0ba-cc7e366a23a1
exl-id: 8eee2ed2-8263-47f2-b928-214fd9ab5f6e
---
# Configuring SSL on Windows Vista {#configuring-ssl-on-windows-vista}

To configure SSL on Windows Vista™, you need an SSL certificate with RSA keys for authentication. You can use the Java keytool to create the certificate.

>[!NOTE]
>
>Windows Vista will not work with DSA keys.

You can run keytool by using a single command that includes all the information that is required to create the certificate and keystore.

**Create an SSL certificate**

1. In a command prompt, navigate to *[JAVA HOME]*/bin and type the following command to create the certificate and keystore:

   `keytool -genkey -keyalg RSA -dname "CN=`*Host Name* `, OU=`*Group Name* `, O=`*Company Name* `,L=`*City******Name* `, S=`*State* `, C=`*Country Code* `" -alias`*"LC Cert"* `-keypass` `*key*`*_**password* `-keystore`*keystorename* `.keystore`

   >[!NOTE]
   >
   >Replace *[JAVA_HOME] with the directory where the JDK is installed, and replace the text in italic with values that correspond with your environment.*

1. Type `changeit` as the password. This password is the default for a Java installation, and the system administrator may have changed it.
