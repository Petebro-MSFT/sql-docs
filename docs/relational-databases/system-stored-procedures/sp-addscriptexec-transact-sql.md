---
description: "sp_addscriptexec (Transact-SQL)"
title: "sp_addscriptexec (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: replication
ms.topic: "reference"
dev_langs: 
  - "TSQL"
f1_keywords: 
  - "sp_addscriptexec"
  - "sp_addscriptexec_TSQL"
helpviewer_keywords: 
  - "sp_addscriptexec"
ms.assetid: 1627db41-6a80-45b6-b0b9-c0b7f9a1c886
author: markingmyname
ms.author: maghan
---
# sp_addscriptexec (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Posts a SQL script (.sql file) to all Subscribers of a publication. This stored procedure is executed at the Publisher on the publication database.  
  
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_addscriptexec [ @publication = ] publication  
    [ , [ @scriptfile = ] 'scriptfile' ]  
    [ , [ @skiperror = ] 'skiperror' ]  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## Arguments  
`[ @publication = ] 'publication'`
 Is the name of the publication. *publication* is **sysname**, with no default.  
  
`[ @scriptfile = ] 'scriptfile'`
 Is the full path to the SQL script file. *scriptfile* is **nvarchar(4000)**, with no default.  
  
`[ @skiperror = ] 'skiperror'`
 Indicates whether the Distribution Agent or Merge Agent should stop when an error is encountered during script processing. *SkipError* is **bit**, with a default of 0.  
  
 **0** = the agent will stop.  
  
 **1** = the agent continues the script and ignores the error.  
  
`[ @publisher = ] 'publisher'`
 Specifies a non- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publisher. *publisher* is **sysname**, with a default of NULL.  
  
> [!NOTE]  
>  *publisher* should not be used when publishing from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Remarks  
 **sp_addscriptexec** is used in transactional replication and merge replication.  
  
 **sp_addscriptexec** is not used for snapshot replication.  
  
 To use **sp_addscriptexec**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account must have read and write permissions on the snapshot location and read permissions on the location where any scripts are stored.  
  
 The [sqlcmd utility](/sql/tools/sqlcmd/sqlcmd-utility) is used to execute the script at the Subscriber, and the script is executed in the security context used by the Distribution Agent or Merge Agent when connecting to the subscription database. When the agent is run on a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [osql utility](../../tools/osql-utility.md) is used instead of [sqlcmd](/sql/tools/sqlcmd/sqlcmd-utility).  
  
 **sp_addscriptexec** is useful in applying scripts to subscribers, and uses [sqlcmd](/sql/tools/sqlcmd/sqlcmd-utility) to apply the contents of the script to the Subscriber. However, because Subscriber configurations can vary, scripts tested prior to posting to the Publisher may still cause errors on a Subscriber. *skiperror* provides the ability to have the Distribution Agent or Merge Agent ignore errors and continue on. Use [sqlcmd](/sql/tools/sqlcmd/sqlcmd-utility) to test scripts prior to running **sp_addscriptexec**.  
  
> [!NOTE]  
>  Skipped errors will continue to be logged in the Agent history for reference.  
  
 Using **sp_addscriptexec** to post a script file for publications using FTP for snapshot delivery is only supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers.  
  
## Permissions  
 Only members of the **sysadmin** fixed server role or **db_owner** fixed database role can execute **sp_addscriptexec**.  
  
## See Also  
 [Execute Scripts During Synchronization &#40;Replication Transact-SQL Programming&#41;](../../relational-databases/replication/execute-scripts-during-synchronization-replication-transact-sql-programming.md)   
 [Synchronize Data](../../relational-databases/replication/synchronize-data.md)   
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
