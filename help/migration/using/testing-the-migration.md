---
product: campaign
title: Testing the migration
description: Testing the migration
audience: migration
content-type: reference
topic-tags: migration-procedure
exl-id: 228ee9e4-46a0-4d82-b8ba-b019bc0e7cac
---
# Migration tests{#testing-the-migration}

![](../../assets/v7-only.svg)

## General procedure {#general-procedure}

Depending on your configuration, there are several ways of carrying out migration tests.

You should have a test/development environment to carry out migration tests. Adobe Campaign environments are subject to license: check your license contract or contact your Adobe representative.

1. Stop all developments in progress and carry them over to the production environment.
1. Make a backup of the development environment database.
1. Stop all Adobe Campaign processes on the development instance.
1. Make a backup of the production environment database and restore it as a development environment.
1. Before starting the Adobe Campaign services, run the **freezeInstance.js** cauterization script which lets you clear the database of any objects that were running when the backup was started.

   ```
   nlserver javascript nms:freezeInstance.js -instance:<instance> -arg:<run|dry>
   ```

   >[!NOTE]
   >
   >The command launches by default in **dry** mode, and lists all the requests that were executed by that command, without launching them. To execute cauterization requests, use **run** in the command.

1. Make sure your backups are correct by trying to restore them. Make sure you can access your database, your tables, your data, etc.
1. Test the migration procedure in the development environment.
1. If the migration of the development environment is successful, you can migrate the production environment.

>[!CAUTION]
>
>Due to changes made to the data structure, importing and exporting data packages is not possible between a v5 platform and a v7 platform.


## Migration tools {#migration-tools}

Various options let you measure the impact from a migration and identify the potential problems. These options are to be executed:

* in the **config** command:

  ```
  nlserver.exe config <option> -instance:<instanceName>
  ```

* or at the postupgrade:

  ```
  nlserver.exe config -postupgrade <option> -instance:<instanceName>
  ```

>[!NOTE]
>
>* You must use the **-instance:`<instanceame>`** option. We do not recommend using the **-allinstances** option.
>* The Adobe Campaign update command (**postupgrade**) lets you synchronize resources and update schemas and the database. This operation can only be carried out once and only on the application server. After synchronizing resources, the **postupgrade** command lets you detect whether the synchronization generates any errors or warnings.

### Non-standard or missing objects

* The **-showCustomEntities** option displays the list of all non-standard objects:

  ```
  nlserver.exe config -showCustomEntities -instance:<instanceName>
  ```

  Example of a sent message:

  ```
  xtk_migration:opsecurity2 xtk:entity
  ```

* The **-showDeletedEntities** option displays the list of all the standard objects that are missing in the database or the file system. For each missing object, the path is specified.

  ```
  nlserver.exe config -showDeletedEntities -instance:<instanceName>
  ```

  Example of a sent message:

  ```
  Out of the box object 'nms:deliveryCustomizationMdl' belonging to the 'xtk:srcSchema' schema has not been found in the file system.
  ```

### Verification process {#verification-process}

Integrated as standard in the postupgrade command, this process lets you display warnings and errors that could make the migration fail. **If errors are displayed, the migration has not been executed.** If this happens, correct all the errors then re-start the postupgrade.

You can start the verification process on its own (without migration) using the command:

```
nlserver.exe config -postupgrade -check -instance:<instanceName>
```

>[!NOTE]
>
>You can ignore all warnings and errors with the JST-310040 code.

The following expressions are searched for (case sensitive):

<table> 
 <thead> 
  <tr> 
   <th> Expression<br /> </th> 
   <th> Error code<br /> </th> 
   <th> Log type<br /> </th> 
   <th> Comments<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> .@<br /> </td> 
   <td> PU-0001<br /> </td> 
   <td> Warning<br /> </td> 
   <td> This type of syntax is no longer supported in delivery personalization. <br /> </td> 
  </tr> 
  <tr> 
   <td> common.js<br /> </td> 
   <td> PU-0002<br /> </td> 
   <td> Warning<br /> </td> 
   <td> This library must not be used.<br /> </td> 
  </tr> 
  <tr> 
   <td> logon(<br /> </td> 
   <td> PU-0003<br /> </td> 
   <td> Warning<br /> </td> 
   <td> This connection method must be no longer be used.<br /> </td> 
  </tr> 
  <tr> 
   <td> new SoapMethodCall(<br /> </td> 
   <td> PU-0004<br /> </td> 
   <td> Warning<br /> </td> 
   <td> This function is only supported when it is used in JavaScript code executed from a security zone that is in <strong>sessionTokenOnly</strong> mode.<br /> </td> 
  </tr> 
  <tr> 
   <td> sql=<br /> </td> 
   <td> PU-0005<br /> </td> 
   <td> Error<br /> </td> 
   <td> This type of error leads to a migration failure.<br /> </td> 
  </tr> 
  <tr> 
   <td> crmDeploymentType="onpremise"<br /> </td> 
   <td> PU-0007<br /> </td> 
   <td> Error<br /> </td> 
   <td> This type of deployment is no longer supported. Office 365 and On-premise Microsoft CRM connector deployment type have now been deprecated. 
   </br>If you are using one of these deprecated deployment types in an external account, this external account should be deleted and you should then run the <b>postupgrade</b> command. 
   </br>To change to Web API deployment, refer to <a href="../../platform/using/crm-ms-dynamics.md#configure-acc-for-microsoft" target="_blank">Web applications</a>.<br /> </td>
  </tr> 
  <tr> 
   <td> CRM v1(mscrmWorkflow/sfdcWorkflow)<br /> </td> 
   <td> PU-0008<br /> </td> 
   <td> Error<br /> </td> 
   <td> Microsoft CRM, Salesforce, Oracle CRM On Demand action activities are no longer available. To configure the data synchronization between Adobe Campaign and a CRM system, you need to use the <a href="../../workflow/using/crm-connector.md" target="_blank">CRM connector</a> targeting activity.<br /> </td>
  </tr> 
 </tbody> 
</table>

A database and schema coherence check is also carried out.

### Restoration option {#restoration-option}

This option lets you restore out-of-the-box objects if they had been modified. For each restored object, a backup of your changes is stored in the selected folder:

```
nlserver.exe config -postupgrade -restoreFactory:<backupfolder> -instance:<instanceName>
```

>[!NOTE]
>
>We strongly recommend using absolute folder paths and keeping the folder tree structure. For example: backupFolder\nms\srcSchema\billing.xml.

### Resume the migration {#resuming-migration}

If you restart the postupgrade after a migration failure, it resumes from the same place it was stopped.
