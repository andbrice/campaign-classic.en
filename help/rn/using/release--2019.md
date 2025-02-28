---
product: campaign
title: Campaign Classic 2019 releases
description: Learn more about Campaign Classic 2019 releases
hidefromtoc: yes
exl-id: 8a36a542-e095-4208-b624-e59845592863
---
# 2019 releases{#release-2019}

![](../../assets/v7-only.svg)

## Release 19.2{#release-19-2}

### ![](assets/do-not-localize/limited_2.png) Release 19.2.4 - Build 9082 {#release-19-2-4-build-9082}

_April 15, 2021_

* Fixed a client console regression which caused persistent error messages on the IMS connection screen. (NEO-34821)

**Console upgrade only is mandatory. No server upgrade is required.**

>[!NOTE]
>
> Connect to [Adobe Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) to download the new version. Learn how to propose the console update to all end users [in this page](../../installation/using/client-console-availability-for-windows.md).

_March 22, 2021_

* Fixed a regression preventing the usage of some components of the console, such as the date picker and images management in deliveries. (NEO-31453, NEO-31454)

**Console upgrade only is mandatory. No server upgrade is required.** 

>[!NOTE]
>
> Connect to [Adobe Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) to download the new version. Learn how to propose the console update to all end users [in this page](../../installation/using/client-console-availability-for-windows.md).

_December 23, 2020_

>[!CAUTION]
>
> * This release comes with a new connection protocol: if you are connecting to Campaign through Adobe Identity Service (IMS), upgrade is mandatory for both Campaign server and client console to be able to connect to Campaign after **June 30, 2021**. [Learn more](../../technotes/using/ims-updates.md)
>
> * This release comes with a [security fix](https://helpx.adobe.com/security/products/campaign/apsb21-04.html): upgrade is mandatory to reinforce your environment security. 


* The connection protocol has been updated to follow the new IMS authentication mechanism. 
* Fixed a security issue to reinforce protection against Server Side Request Forgery (SSRF) issues. (NEO-27777)

### ![](assets/do-not-localize/red_2.png) Release 19.2.3 - Build 9081 {#release-19-2-3-build-9081} 

_February 7, 2020_

**Improvements**

* Fixed a regression issue due to the implementation of SSL certification which caused the user connection to fail on Windows server. (NEO-20629)
* Fixed an issue which displayed an incorrect version tag number in the **About** menu.


### ![](assets/do-not-localize/red_2.png) Release 19.2 - Build 9080 {#release-19-2-build-9080} 

_December 2, 2019_

**What's new?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA is the State of California’s new privacy law that harmonizes and modernizes data protection requirements going into effect on Jan 01, 2020. CCPA applies to Adobe Campaign customers who hold data for Data Subjects residing in California.</p>
    <p>In addition to the privacy capabilities already available (including consent management, data retention settings, and user roles), Adobe Campaign helps facilitate your readiness for CCPA:</p>
    <ul>
      <li>Right to Access and Right to Delete: we are leveraging the capabilities that were added for GDPR. <a href="https://helpx.adobe.com/campaign/kb/acc-privacy.html#righttoaccess">Read more</a></li>
      <li>You can track whether a consumer has opted-out for the sale of Personal Information. For this, you need to extend the Profiles table and add an <strong>Opt-Out for CCPA</strong> field. <a href="https://helpx.adobe.com/campaign/kb/acc-privacy.html#ccpa">Read more</a></li></td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Workflow live monitoring</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>You can now monitor the execution status of all workflows on your instance using predefined views.</p>
   <p>For more information, refer to the <a href="../../workflow/using/monitoring-workflow-execution.md#filtering-workflows-status">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>Interactive content with AMP</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
<td> <p>Adobe Campaign enables you to try out the new interactive <a href="https://amp.dev/about/email/">AMP for Email</a> format, which allows marketers to include AMP components inside messages to enhance the email experience with rich, dynamic and interactive content, directly actionable in the message itself.</p>
   <p>This capability is released as a public beta.</p>
   <p>For more information, refer to the <a href="../../delivery/using/defining-interactive-content.md">detailed documentation</a> and the <a href="https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/sending-messages/email-channel/defining-interactive-email-content-with-amp.html">tutorial video</a>.</p><br /></td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>Secure SMS Messaging (TLS)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
<td> <p>Secured SMS is now supported through the Extended Generic SMPP Connector. This allows an encrypted connection to the provider.</p> <p><strong>Warning</strong> This feature requires an up-to-date certificate on all servers. Invalid, revoked or expired certificates will generate errors affecting the overall SMS sending capabilities.</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html">detailed documentation</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Security enhancements**

* Fixed Stored Cross Site Scripting vulnerabilities in Campaign interface – input data validation and output encoding. (NEO-16810)
* Fixed a security issue on profile authorization which could allow access to unauthorized data, by reinforcing login restriction policy. (NEO-14445)

**Improvements**

* Memory consumption optimization for Push Notifications.
* For performance and storage optimization, the handling of the **logins.log** file has been enhanced. The file is now split into multiple files, one each day with a maximum of 365 files retained. [Read more](../../production/using/log-files.md)
* Microsoft Dynamics CRM external account can now be configured using password credentials (password + username) or certificate (private key). [Read more](../../installation/using/external-accounts.md#microsoft-dynamics-crm-external-account)
* Some enhancements have been added to the Hadoop FDA connector to improve reliability
* A specific guardrail has been added to check disk space before allowing to upload public resources on the server.
* New [Campaign Options](../../installation/using/configuring-campaign-options.md) have been added:
    * The **WdbcKillSessionPolicy** configuration option allows you to affect **Unconditional Stop** behavior on all the workflows and PostgreSQL database queries. 
    * The **NmsOperation_DeliveryPreparationWindow** option allows you to define the number of days above which deliveries with inconsistent status will be excluded from the count of running deliveries.
    * The **WdbcOptions_TempDbName** option allows you to configure a separate database for working tables on Microsoft SQL Server. This optimizes backups and replication. [Read more](../../production/using/rdbms-specific-recommendations.md#microsoft-sql-server)
    * The **XtkCleanup_NoStats** option has been enhanced for PostgreSQL to better control the behavior of the storage optimization step of the database cleanup workflow. [Read more](../../production/using/database-cleanup-workflow.md#statistics-update)
* An account lockout mechanism has been added to the **logon()** API. It prevents any further login attempts after a certain number of consecutive failed login attempts within a specified timeframe.
* A new **Maximum personalization run time** option in the delivery properties allows you to define a time-out period for the personalization run time, in order to prevent the personalization phase from running for too long. [Read more](../../delivery/using/personalization-fields.md#timing-out-personalization)
* The **ftp protocol** option has been added to allow you to use a proxy configuration for SFTP connections. [Read more](../../installation/using/file-res-management.md)
* New support of proxy access to an SFTP external server for on-premise environments.
* A specific guardrail has been added to prevent installation of packages which are not compatible with the Campaign instance. [Read more](../../installation/using/installing-campaign-standard-packages.md)

_Deprecated systems_

The following systems are now [deprecated](deprecated-features.md) for Campaign Classic implementations:
* Apache 2.2 
* Centos 6 

Please ensure you are on supported versions of any systems listed in the latest Campaign Compatibility matrix. [Read more](https://helpx.adobe.com/campaign/kb/compatibility-matrix.html)

_Campaign Mobile SDK_

The build 1.0.26 of the iOS SDK is now available. In this new build, we’ve added the support of iOS 13. This new version now supports notification priority and the new registration token management process for iOS 13 Push notifications. If you’re running applications on a previous version of the SDK, you need to recompile your applications with the new SDK. To get the SDK, please contact [Adobe Customer Care](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

**Patches**

* Fixed a crash issue when the **Add linked table** field was empty in the **Data Loading (RDBMS)** workflow activity. (NEO-12213)
* Fixed an issue which could lead to certain messages not being processed by the Mid-Sourcing server. (NEO-12395)
* Fixed an issue in the database cleanup workflow when using the query banding option with Teradata. (NEO-12399)
* Fixed an issue affecting delivery analysis with typology rule including ne.jp domain. (NEO-12609)
* Fixed an issue related to SMS over TLS updates which were implying to a more restrictive certificate policy. These updates could lead to a connection failure between marketing and mid-sourcing servers in case of an out-of-date certificate. (NEO-17698) 
* Fixed an issue when using the **Test connection** button on an external account in a mid-sourcing environment with Vault authentication. (NEO-12722)
* Fixed an issue on queries using date functions with an FDA Hadoop connection. (NEO-12847)
* Fixed an issue when replacing an image in the email editor. (NEO-13098)
* Fixed an issue which could lead to post-upgrade errors on folders which had been deleted or moved to another location. (NEO-13118)
* Fixed an issue on image display when using the **Define image per device screen size** option on LINE messages. (NEO-13228)
* Fixed a delivery preparation issue when the **Exclude duplicate address during delivery** option is unselected. (NEO-13240)
* Fixed an issue in workflows when using the **File transfer** activity to download files using the **Delete the source files after transfer** option, with name containing a space character. (NEO-13411)
* Fixed an issue with Tomcat cache cleanup which could lead to memory issues. (NEO-13456)
* Fixed an issue when installing the **Control of offer engine with execution instance** built-in package on an existing control instance running in Microsoft SQL 2017. (NEO-13539)
* Fixed a console crash issue that could occur when unchecking tracked URLs in an email, from the **Text content** tab due to a non-initialized variable. (NEO-13545)
* Fixed an encoding issue on Chinese sender name. (NEO-13837)
* Fixed an error which could raise when displaying survey response data from the Explorer. (NEO-14590)
* Fixed an issue which could lead to discrepancy between the delivery log classification and the quarantine table. (NEO-16547)
* Fixed an issue with DKIM keys which were not embedded into emails. (NEO-16804)
* Fixed an issue which was displaying the wrong error code when an invalid session token was used in the context of API calls to trigger events. The error code was 'HTTP 200 OK' instead of 'HTTP 403 Forbidden'. (NEO-16826)
* Fixed an issue when displaying delivery reports via web access. (NEO-17015)
* Fixed an IMS authentication issue when login to Adobe Campaign. (NEO-17312)
* Fixed an issue which prevented quarantined emails from being deleted by the Privacy Management process. (NEO-17314)
* Fixed throughput issues after upgrading to 9031 with SQL database. (NEO-17558)
* Fixed an issue which affected the CRM Connector with Salesforce. (NEO-17712)
* Fixed a timeout issue when importing data from an external SFTP. (NEO-19723)
* Fixed an issue when accessing to Predictive models. (NEO-19713)
* Fixed an issue affecting random sampling in **Split** workflow activity with Hadoop FDA database. (NEO-16636)
* Fixed a regression on Oracle causing some functions to be considered as invalid after postupgrade. (NEO-12759)


## Release 19.1{#release-19-1}

### ![](assets/do-not-localize/limited_2.png) Release 19.1.8 - Build 9039 {#release-19-1-8-build-9039}

_April 15, 2021_

* Fixed a client console regression which caused persistent error messages on the IMS connection screen. (NEO-34821)
* Fixed a regression that could block the workflow data export to an FDA database (Teradata, Snowflake).

**Console upgrade only is mandatory. No server upgrade is required.** 

>[!NOTE]
>
> Connect to [Adobe Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) to download the new version. Learn how to propose the console update to all end users [in this page](../../installation/using/client-console-availability-for-windows.md).

_March 22, 2021_

* Fixed a regression preventing the usage of some components of the console, such as the date picker and images management in deliveries. (NEO-31453, NEO-31454)

**Console upgrade only is mandatory. No server upgrade is required.** 

>[!NOTE]
>
> Connect to [Adobe Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) to download the new version. Learn how to propose the console update to all end users [in this page](../../installation/using/client-console-availability-for-windows.md).

_December 16, 2020_

>[!CAUTION]
>
> * This release comes with a new connection protocol: if you are connecting to Campaign through Adobe Identity Service (IMS), upgrade is mandatory for both Campaign server and client console to be able to connect to Campaign after **June 30, 2021**. [Learn more](../../technotes/using/ims-updates.md)
> * This release comes with a [security fix](https://helpx.adobe.com/security/products/campaign/apsb21-04.html): upgrade is mandatory to reinforce your environment security. 
> * If you are using the Experience Cloud Triggers integration through oAuth authentication, you need to move to Adobe I/O as described [in this page](../../integrations/using/configuring-adobe-io.md). Legacy oAuth authentication mode with Campaign [has been retired](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-legacy-api-end-of-life-notice/td-p/385411) on **September 2021**. Hosted environments benefit from an extension until  **February 23, 2022**. As an on-premise or hybrid customer, contact Adobe Customer Care to extend support to February 2022. You must provide [the AppID of the OAuth application](../../integrations/using/configuring-pipeline.md?lang=en#step-optional) to Adobe.


**Improvements**

* The connection protocol has been updated to follow the new IMS authentication mechanism. 
* Triggers integration authentication originally based on oAUTH authentication setup to access pipeline has been changed and moved to Adobe I/O. [Learn more](../../integrations/using/configuring-adobe-io.md)
* Following the end of support for iOS APNs legacy binary protocol, all instances using this protocol are updated to HTTP/2 protocol during postupgrade.
* Fixed a security issue to reinforce protection against Server Side Request Forgery (SSRF) issues. (NEO-27777)
* Fixed an issue causing the deactivation of the SMPP connector after a connection error, preventing other SMS deliveries from being sent and leading to performance issues.
* Fixed an issue that displayed incorrect percentages when generating a descriptive report via a workflow activity. (NEO-14314)
* Fixed a delivery preparation issue when the **Exclude duplicate address during delivery** option was unselected. (NEO-13240)
* Fixed an issue that could cause workflows to fail when running an **Enrichment** activity. (NEO-17338)
* Fixed an issue in workflows when fetching records from an external database and inserting them in the Campaign database. (NEO-26359)
* Fixed a server crash issue by preventing memory corruption when cleaning the expression parser.
* Fixed an issue which prevented the **NoNull** function from working in Oracle databases after upgrading to build 9032. (NEO-26488)
* Fixed an issue when editing a campaign template description that prevented the **Save** button from displaying when copy-pasting symbols like, for example, Japanese characters. (NEO-27071)
* Fixed an issue which prevented the description of a campaign or campaign template from being saved when clicking outside of the window before clicking the **Save** button. (NEO-27449)
* Fixed an issue at the proxy configuration level that prevented you from logging into Adobe Campaign after the latest Windows 10 update. (NEO-27813)
* Fixed an issue related to the management of empty lines in log files, causing failures in the MTA process behavior and leading to performance drops in delivery sending.

**Technical evolutions**

Tomcat has been updated from version 7 (7.0.103) to version 8 (8.5.57). The `tomcat-7` directory is replaced with a `tomcat-8` directory. On windows, _iis_neolane_setup.vbs_ and _apache_neolane.conf_ are now installed in the `conf` directory (instead of `tomcat-7/conf` previously). On linux, _apache_neolane.conf_ is now installed in the `conf` directory.

On Linux, the nlserver service startup now uses a systemd unit instead of the /etc/init.d/nlserver6 script. The migration to the new startup scheme is performed automatically when you install the 19.1.8 package. The /etc/init.d/nlserver6 is still provided but for interacting with the nlserver service (start, restart, stop, etc.), we recommend that you use the systemctl command directly.


### ![](assets/do-not-localize/red_2.png) Release 19.1.7 - Build 9036 {#release-19-1-7-build-9036}

_September 15, 2020_

**Improvements**

* Improved nlsrvmod for Apache 2.4 thread usage to fix nlsrvmod crashes. 
* Fixed an issue when using the File Transfer activity with an Azure external account and an SSL encryption. The connection was performed through HTTP instead of HTTPS. (NEO-26720)
* Fixed an issue with the url cache mechanism which did not retrieve the label or category.
* Fixed an issue which led to mirror page URLs being incorrectly defined in email deliveries (due to improper ASCII character control). (NEO-26084)
* The jarsToSkip list in catalina.properties has been updated to remove the reference to a jar file that was no longer used (iOS notifications).
* Fixed a regression issue which prevented after publication after postupgrade.
* Fixed a regression with out-of-the-box delivery reports which appeared truncated when exported to PDF. (NEO-25757)
* Fixed an issue that deleted the encoding parameter value when redirecting from a tracking URL (impact on Japanese characters). (NEO-25637)
* Fixed an issue which led to unsigned links from personalized domains being blocked when they should be allowed. (NEO-25210)
* Fixed a regression impacting calculated fields in a workflow causing the workflow to fail. (NEO-25194)
* Fixed a compatibility issue with Microsoft Dynamics (from version 8.2) that could prevent some API calls from executing (RetrieveAllEntities). (NEO-24528)
* Fixed a regression issue when using the ACS Connector feature which prevented the connection to a Campaign Standard instance (incorrect management of the FOH/FOH2 connection). (NEO-23433)
* Fixed a regression issue on database connection causing the web server to constantly restart due to a database encoding problem. This could lead to overconsumption. (NEO-23264)
* Fixed an issue with the database cleanup workflow which could fail due to unmanaged data source. (NEO-23160, NEO-23364)
* The cleanup workflow now purges expired lists by batches of 100 instead of one by one.
* Following the switch to the new sequence ID mechanism, all web applications that are updating the recipient table are republished during postupgrade.
* Fixed an issue preventing emails from being sent when there was Javascript code outside of the HTML content tag. (NEO-18628)
* Fixed an issue that prevented the transactional messages tracking indicators from being updated by the Tracking workflow. (NEO-17770)
* Improved the performance of the database update wizard to make fewer SQL statements in order to optimize response time.
* Fixed a console crash issue that could occur when unchecking tracked URLs in an email, from the **Text content** tab due to a non-initialized variable. (NEO-13545)
* Fixed an issue which prevented you from uploading files in a File Transfer activity using an Azure Blob Storage external account due to a non-initialized variable (m_pCurlReader). (NEO-13717)
* Fixed a postupgrade issue which turned off Apache and the web server before the web application republication. (NEO-27155)
* Fixed a regression which led to an incorrect timezone being picked when setting time in a **Scheduler** workflow activity.


### ![](assets/do-not-localize/red_2.png) Release 19.1.6 - Build 9035 {#release-19-1-6-build-9035}

>[!CAUTION]
>
>This build is for on-premise installations only. For hybrid deployments, hosted instances will keep running the 9032 build. Do not upgrade your marketing instance to the 9035 build as it is not compatible with 9032.

_October 3, 2019_

**Improvements**

* Fixed an issue when using the CRM Connector for Salesforce. (NEO-17712)
* Fixed an index issue which could cause performance issues when sending transactional messages.
* Fixed a performance isssue when sending messages. (NEO-17558)
* Fixed an issue which could lead to certain messages not being processed by the Mid-Sourcing server. (NEO-12395)
* Fixed an issue which prevented the full use of the SQL Data Management activity (the "SQL Data Management" named right was missing).

### ![](assets/do-not-localize/red_2.png) Release 19.1.5 - Build 9033{#release-19-1-5-build-9033}

_August 13, 2019_

**Improvements**

* Fixed an issue with the SQL statement 'SELECT COUNT' which was executed on the default database rather than the FDA database during Data extraction in Data Management activity.
* To improve customer infrastructure capabilities, an SFTP proxy declaration is now available in the server configuration file.
* Fixed a crash issue when the **Add linked table** field was empty in the **Data Loading (RDBMS)** workflow activity. (NEO-12213)
* Fixed an issue with the midEmitter package installation through command line.
* A new authentication option has been added to support OAuth credentials within the AC connector with Microsoft Dynamics. (NEO-11982)
* Fixed an issue with UUID (Unique Universal Identifier) management causing the Query and Data loading workflow activities to fail with Hive FDA.
* Fixed a regression on Oracle causing some functions to be considered as invalid after postupgrade. (NEO-12759)
* Fixed a regression leading to an incorrect time zone being picked when setting the time in a Scheduler workflow activity.

### ![](assets/do-not-localize/green_2.png) Release 19.1.4 - Build 9032{#release-19-1-4-build-9032}


>[!NOTE]
>
>19.1.4 [!DNL Gold Standard] releases are listed in this [page](../../rn/using/gold-standard.md).


### ![](assets/do-not-localize/red_2.png) Release 19.1.2 - Build 9029{#release-19-1-2-build-9029}

_June 21, 2019_

**Security enhancements**

* To optimize security, the Java library (Netty) has been updated to the latest version (4.1.34). (NEO-12788)

**Improvements**

* Fixed a regression linked to sdomain column management which prevented emails from being sent on certain configurations. 
* To improve performance, a _operation="none" attribute has been added to rtEvent SOAP calls to avoid "SELECT FOR UPDATE" requests.
* Fixed a workflow display issue with outbound transitions after the Test activity. (NEO-12727)
* We now allow the deletion of dummy records created in Microsoft Dynamics during import workflow.
* Improved permissions to execute the security zone package when using internal account.


### ![](assets/do-not-localize/red_2.png) Release 19.1 - Build 9026{#release-19-1-build-9026}

_May 30, 2019_

**What's new?**

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Control Panel<br /> </td> 
   <td> <p>To increase efficiency in your work as an Admin user, manage settings of your SFTP servers by monitoring storage, add IP addresses to allowlist, and installing SSH keys for each instance. Please note Control Panel is only available for customers hosted on AWS as of today (<a href="https://experiencecloud.adobe.com/campaign/controlpanel/">login through the Experience Cloud today</a>).</p> <p>For more information, refer to the <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html">detailed documentation</a> and the <a href="https://experienceleague.adobe.com/docs/campaign-classic-learn/control-panel/control-panel-overview.html">how-to video</a>. </p><p>Note: upgrading to the latest Campaign build is not required to access the Control Panel.</p> </td> 
  </tr> 
    <tr> 
   <td> Audit trail<br /> </td> 
   <td> <p>As admin, increase productivity by monitoring and managing changes made within the Adobe Campaign Classic instance. The Audit Trail will log actions made on Source Schemas, Workflows and Options. You can quickly see if an element has been created, modified or deleted.</p><p>For more information, refer to the <a href="../../production/using/audit-trail.md">detailed documentation</a> and <a href="https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/monitoring/audit-trail.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Guardrail, Robustness &amp; Scalability<br /> </td> 
   <td> A series of improvements has been added to Campaign Classic. Guardrail, robustness and scalability improvements are listed below.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compatibility Matrix Update<br /> </td> 
   <td> With this new version, Adobe Campaign now supports the following database systems. Refer to the <a href="https://helpx.adobe.com/campaign/kb/compatibility-matrix.html">Compatibility Matrix</a>.<br /> 
    <ul> 
     <li> <p>Oracle 18c</p> </li> 
     <li> <p>MySQL 5.7 (FDA)</p> </li> 
     <li> <p>SQL Server 2017</p> </li> 
     <li> <p>Teradata 16 (FDA)</p> </li> 
     <li> <p>PostgreSQL 11</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Security enhancements**

* For security reasons, you can no longer insert arbitrary commands when using the **[!UICONTROL Pre-process the file]** option in a **[!UICONTROL Data loading (file)]** workflow activity. A drop-down list is now available allowing you to select from 3 options: **[!UICONTROL None]**, **[!UICONTROL Decompression]** (zcat) or **[!UICONTROL Decrypt]** (gpg). The XtkSecurity_Disable_Preproc security flag has been added. For new customers, this option will be set to 0. For existing customers, this option will be set to 1 by the postupgrade in order to keep the previous behavior. Refer to this [section](../../workflow/using/data-loading--file-.md).
* Fixed a password visibility issue that occurred when testing the connection of an FDA external account with no time zone set.
* The PDFBox library has been removed.
* Tomcat has been updated to version 7.0.93.
* Fixed a token visibility issue that occurred when the security token was invalid.
* Fixed a potential XTK injection issue in the WSDL JSP (schemawsdl.jsp).
* The credential and password storage in the application's source code and memory has been optimized. 
* PII view restriction has been optimized. (NEO-12339, NEO-12396, NEO-12398, NEO-12339, NEO-12667)
* Fixed inconsistency issues in secret key management.
* The same generic error is now displayed for failed login attempts with a valid or invalid username.
* The naming of uploaded files has been enhanced. 
* A new XtkSecurity_Disable_GetSetEnv option has been added to block the use of setEnv and getEnv functions.
* Sensitive information is now hidden in the application stack trace.

**Guardrail, robustness &amp; scalability improvements**

* Lifespan - XtkNewId sequence usage optimization: the most consuming tables have been moved from the xtkNewId sequence to dedicated sequences.
* FDA over HTTP v2: the FDA over HTTP protocol is widely used on Hybrid deployments, especially for broadLog retrieval and delivery preparation. Robustness has been enhanced to avoid network issues and possible errors as retrieving or pushing data. This requires that builds at both ends of the connection are up-to-date, otherwise the old protocol will still be used.
* Tracking workflow: the tracking workflow robustness has been enhanced. Several issues related to tracking log inserts/updates and URL tracking customization have been fixed. In addition, the tracking workflow now detects tracking log issues that could lead to errors and stop the workflow. These issues are now discarded and not processed.
* Cleanup workflow: the cleanup workflow has been improved to avoid potential errors and stops. This optimizes database size and performance.
* Embedded images in transactional messages: we have added the full support of embedded images in transactional messages, to avoid possible crashes or missing images.
* Database size - XtkJobLog: a purge mechanism has been added to this table. This has a positive impact on the database size.
* BCC archiving: the default parameters for BCC archiving have been changed to increase archiving velocity. [Read more](../../installation/using/email-archiving.md#parameters)
* Database structure update: SQL requests generated by the Database Structure Update Wizard have been improved for faster execution.
* Guardrails for operator actions: several guardrails have been implemented to prevent operators from performing actions which could impact the platform's integrity. Built-in schemas can no longer be deleted through the interface. Also, the workflow source XML can no longer be edited by non-admin users.
* Two new options have been made available: **XtkSecurity_Restrict_EditXML** (allows you to disable the edition of deliveries’ XML code) and **NmsOperation_OperationMgtDebug** (allows you to monitor the operationMgt technical workflow execution). [Read more](../../installation/using/configuring-campaign-options.md)

**Other changes**

* Push notifications: we now support the Thread ID option for iOS push.
* Improved the management of long name indexes which could cause postupgrade issues.
* Now, during the analysis of a decomail delivery, if the publication mode is set to **[!UICONTROL None]** in the deployment wizard, an error is logged and the analysis is stopped: "Publication mode is set to 'none': Cannot embed image. Images won't be displayed on feature phone." (NEO-12208)
* The broadlog management has been improved for transactional messaging. When broadlogs are synchronized from the execution instance to the control instance, the @lastModified field is updated to the system’s current date. The MC_Update_BlLastModified option has been added for control instances. True means that the current date will be used on the control instance (default behavior). False means that we use the execution instance broadlog’s @lastModified date. (NEO-12579)
* Indexes were added in the coupon temporary tables to optimize delivery sending. (NEO-12437)
* In the Analytics integration, the retrieval of AAM segment data with % character is now allowed. (NEO-12025)
* Removed the 10,000 record limit in Workflow Heatmap to fix a missing data issue. (NEO-12329)
* Open Office is not supported and is now fully removed from the application. If you were still using it, move to Libre Office as it will not work anymore starting 19.1.
* You can now limit Write access to Update data activity in Workflow using sysfilter attributes. [Read more](../../configuration/using/filtering-schemas.md)

**Patches**

* Fixed an issue which prevented the certificate from being uploaded for iOS mobile push notifications.
* Fixed potential recurrent server crashes for transactional push notifications. Other crash issues have been fixed.
* Fixed an issue which caused reporting discrepancies between user activities and tracking reports for the open delivery indicator. (NEO-11742)
* Fixed an issue with the IMS login.
* Fixed an issue which could lead to missing images in a delivery when adding an image from the library. (NEO-11900)
* Fixed an issue that could occur when extracting offer details in a direct mail delivery. (NEO-11700)
* Fixed an issue that could affect SMS transactional message performance. (NEO-9812)
* Fixed a console crash that could occur when using the Defined in an external file option for the main target of a delivery. (NEO-12349)
* Fixed an issue when analyzing a message which targeted recipients for Japanese (.JP) domains. (NEO-12246)
* Fixed a display issue when using a distribution of values with a 1:N link. (NEO-12212, NEO-11820)
* Fixed an issue which could cause NmsMxDomain errors in the MTA logs after a postupgrade. (NEO-12752)
* Fixed an issue when using the "Keep all additional data from the main set" option in an enrichment workflow activity. (NEO-13291)
* Fixed a Tomcat crash issue when sending push notifications using HTTP2. (NEO-12701)
* Fixed an issue with the HTTPRequest API which did not wait for all callbacks to finish. (NEO-12628)
* Fixed an issue with the computing process of tracking indicators for transactional messages. (NEO-12529)
* Fixed an issue with the use of themes in offer management. (NEO-11804)
* Fixed a performance issue when sending push notifications. (NEO-11787)
* FIxed an issue when previewing an outbound XML or CSV file in offer management for a direct mail delivery. (NEO-11290)
* Fixed an issue when installing the **Managing social networks** (Social Marketing) package. (NEO-12081)
* Fixed an issue which prevented you from deleting a web application even if you had the correct access rights. (NEO-12072)
* Fixed an issue which could cause some values to be overwritten when exporting and then importing an object via XML. The XtkExport_IncludeDefaultValues option has been added. When set to True (default behavior), all values are exported. When set to False, modifications are overwritten with the default value. (NEO-11979)
* Fixed an issue which caused the **[!UICONTROL Alert]** workflow activity to fail when an enrichment activity was added after a query. (NEO-12132)
* Fixed an issue on Oracle setups where pipeline (triggers) offsets were not retrieved successfully from the database causing duplicates. (NEO-12121)
* Fixed an issue which could cause diplay errors in pivot tables when using the Analytics integration (NEO-12103)
* Fixed an issue with the Descriptive Analysis report. (NEO-11414)
* Fixed an issue with CRM connectors when the remote table contained a field with an underscore in its name.
* Fixed a issue which could cause a display issue for currency symbols in the Hypothesis reports. (NEO-11634)
* Fixed a redirection and tracking issue when using certain characters in tracking links. 
* Fixed an issue which prevented offer preview from working correctly.
* Fixed an issue with soft bounces not being removed from the address table. 
* Fixed a JAVA error when using barcodes.
* Fixed a translation issue in web applications (NEO-12460)
* Fixed an issue with the s3 File Transfer workflow activity. (NEO-12473)
* Fixed an issue with date fields in web applications. (NEO-12496)
* Fixed an ID exhaustion issue when using seed addresses in a delivery. (NEO-11842)
* Fixed an issue with phantomjs and Debian 9 compatibility.
* Fixed an error when approving the content of a proof. (NEO-12725)
* Fixed an issue with the "Exclude this subset from the population" workflow feature. (NEO-12441)
* Fixed an issue with the HTTPRequest-wait API which did not wait for all callbacks to finish. (NEO-12628)
* Fixed an issue with the "Update Shared Audience" task in a split activity. (NEO-11562)
* Fixed a web server crash issue. (NEO-12904) 
* Fixed an issue with the Nature parameter in transactional templates. (NEO-12334)
* Fixed a console crash issue when displaying the tracked URLs in the email text editor. (NEO-13122)
* Fixed an issue with the Split File activity when importing audiences from Audience Manager. (NEO-11550)
* Fixed an issue which caused errors in the hot click report. (NEO-11459)
* Fixed an issue with offer rendering. (NEO-11565)
* Fixed an issue with the List Update activity when importing audiences from Audience Manager. (NEO-11226)
* Fixed an issue with the Schedule activity and time zone configuration. (NEO-11662)
* Fixed an issue that caused the tracking workflow to fail in case of malformed URLs. 
* Fixed an issue with external accounts after importing the mobile application package.
* Fixed an issue when assigning a time zone to an operator. (NEO-12464)
* Fixed an issue which could cause errors in the mtachild logs. (NEO-11539, NEO-8978)
* Fixed an issue when clicking the History icon in a saved report. (NEO-11620)
* Fixed an issue when editing a pivot table in a report. (NEO-12068)
