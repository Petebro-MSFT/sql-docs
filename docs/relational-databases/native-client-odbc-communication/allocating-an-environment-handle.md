---
description: "Allocating an Environment Handle"
title: "Allocating an Environment Handle | Microsoft Docs"
ms.custom: ""
ms.date: "03/16/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: native-client
ms.topic: "reference"
helpviewer_keywords: 
  - "SQL Server Native Client ODBC driver, environment handles"
  - "ODBC applications, connections"
  - "handles [SQL Server Native Client]"
  - "environment handles [SQLNCLI]"
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: markingmyname
ms.author: maghan
monikerRange: ">=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# Allocating an Environment Handle
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle. This is the global context handle and placeholder for the other handles in ODBC. You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.  
  
 After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using. To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../../relational-databases/native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.  
  
## See Also  
 [Communicating with SQL Server &#40;ODBC&#41;](../../relational-databases/native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
  
