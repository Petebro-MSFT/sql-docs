---
description: "sp_gettopologyinfo (Transact-SQL)"
title: "sp_gettopologyinfo (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: replication
ms.topic: "reference"
dev_langs: 
  - "TSQL"
f1_keywords: 
  - "sp_gettopologyinfo_TSQL"
  - "sp_gettopologyinfo"
helpviewer_keywords: 
  - "sp_gettopologyinfo"
ms.assetid: 8bbe8a06-a4aa-4219-8402-12db6a4682c6
author: markingmyname
ms.author: maghan
---
# sp_gettopologyinfo (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Returns information about a peer-to-peer transactional replication topology. Execute [sp_requestpeertopologyinfo](../../relational-databases/system-stored-procedures/sp-requestpeertopologyinfo-transact-sql.md) to collect information before you execute this procedure.  
  
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_gettopologyinfo [ @request_id = ] request_id  
```  
  
## Arguments  
 [ @request_id= ] *request_id*  
 Is the ID of a topology status request. *request_id* is **int**, with a default of NULL. To obtain an ID, use the @request_id output parameter from [sp_requestpeertopologyinfo](../../relational-databases/system-stored-procedures/sp-requestpeertopologyinfo-transact-sql.md) or query the [MSpeer_topologyrequest](../../relational-databases/system-tables/mspeer-topologyrequest-transact-sql.md) system table.  
  
## Result Sets  
 sp_gettopologyinfo returns a result set that has a single XML column. The data in the XML column is the same as the data in the [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md) system table.  
  
## Return Code Values  
 **0** (success) or **1** (failure)  
  
## Remarks  
 sp_gettopologyinfo is used in peer-to-peer transactional replication. Execute [sp_requestpeertopologyinfo](../../relational-databases/system-stored-procedures/sp-requestpeertopologyinfo-transact-sql.md) before you execute sp_gettopologyinfo. These procedures are used by the Configure Peer-to-Peer Topology Wizard, but they can also be used directly if you require topology information in an XML format. If you prefer tabular results, query the [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md) system table.  
  
## Permissions  
 Requires membership in the sysadmin fixed server role or db_owner fixed database role.  
  
## See Also  
 [Peer-to-Peer Transactional Replication](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md)   
 [Replication Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
