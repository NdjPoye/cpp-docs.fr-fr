---
title: "TN042&#160;: Recommandations du d&#233;veloppeur concernant le pilote ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bases de données (C++), ODBC"
  - "ODBC (pilotes) (C++), écrire"
  - "TN042"
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN042&#160;: Recommandations du d&#233;veloppeur concernant le pilote ODBC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 This note describes guidelines for ODBC driver writers.  It outlines general requirements and assumptions of ODBC functionality that the MFC Database classes make, and various expected semantic details.  Required driver functionality to support the three `CRecordset` Open modes \(**forwardOnly**, **snapshot** and **dynaset**\) are described.  
  
## ODBC's Cursor Library  
 The MFC Database classes present functionality to the user that in many cases surpasses the functionality provided by most level 1 ODBC drivers.  Fortunately, ODBC's Cursor Library will layer itself between the database classes and the driver, and will automatically provide much of this additional functionality.  
  
 For instance, most 1.0 drivers do not support backward scrolling.  The Cursor Library can detect this, and will cache rows from the driver and present them as requested on FETCH\_PREV calls in **SQLExtendedFetch**.  
  
 Another important example of cursor library dependence is positioned updates.  Most 1.0 drivers also do not have positioned updates, but the cursor library will generate update statements which identify a target row on the data source based upon its current cached data values, or a cached timestamp value.  
  
 The class library never makes use of multiple rowsets.  Therefore, the few **SQLSetPos** statements are always applied to row 1 of the rowset.  
  
## CDatabases  
 Each `CDatabase` allocates a single **HDBC**. \(If `CDatabase`'s `ExecuteSQL` function is used, an **HSTMT** is temporarily allocated.\) So if multiple `CDatabase`'s are required, multiple **HDBC**s per **HENV** must be supported.  
  
 The database classes require the cursor library.  This is reflected in a **SQLSetConnections** call **SQL\_ODBC\_CURSORS**, **SQL\_CUR\_USE\_ODBC**.  
  
 **SQLDriverConnect**, **SQL\_DRIVER\_COMPLETE** is used by `CDatabase::Open` to establish the connection to the data source.  
  
 The driver must support **SQLGetInfo SQL\_ODBC\_API\_CONFORMANCE** \>\= **SQL\_OAC\_LEVEL1**, **SQLGetInfo SQL\_ODBC\_SQL\_CONFORMANCE** \>\= **SQL\_OSC\_MINIMUM**.  
  
 In order for transactions to be supported for the `CDatabase` and its dependent recordsets, **SQLGetInfo SQL\_CURSOR\_COMMIT\_BEHAVIOR** and **SQL\_CURSOR\_ROLLBACK\_BEHAVIOR** must have **SQL\_CR\_PRESERVE**.  Otherwise, attempts to perform transaction control will be ignored.  
  
 **SQLGetInfo SQL\_DATA\_SOURCE\_READ\_ONLY** must be supported.  If it returns "Y", no update operations will be performed on the data source.  
  
 If the `CDatabase` is opened ReadOnly, an attempt to set the data source read only will be made with **SQLSetConnectOption SQL\_ACCESS\_MODE**, **SQL\_MODE\_READ\_ONLY**.  
  
 If identifiers require quoting, this information should be returned from the driver with an **SQLGetInfo SQL\_IDENTIFIER\_QUOTE\_CHAR** call.  
  
 For debugging purposes, **SQLGetInfo SQL\_DBMS\_VER** and **SQL\_DBMS\_NAME** are retrieved from the driver.  
  
 **SQLSetStmtOption SQL\_QUERY\_TIMEOUT** and **SQL\_ASYNC\_ENABLE** may be called on a `CDatabase`'s **HDBC**.  
  
 **SQLError** may be called with any or all arguments NULL.  
  
 Of course, **SQLAllocEnv**, **SQLAllocConnect**, **SQLDisconnect** and **SQLFreeConnect** must be supported.  
  
## ExecuteSQL  
 In addition to allocating and freeing a temporary **HSTMT**, `ExecuteSQL` calls **SQLExecDirect**, **SQLFetch**, **SQLNumResultCol** and `SQLMoreResults`.  **SQLCancel** may be called on the **HSTMT**.  
  
## GetDatabaseName  
 **SQLGetInfo SQL\_DATABASE\_NAME** will be called.  
  
## BeginTrans, CommitTrans, Rollback  
 **SQLSetConnectOption SQL\_AUTOCOMMIT** and **SQLTransact SQL\_COMMIT**, **SQL\_ROLLBACK** and **SQL\_AUTOCOMMIT** will be called if transaction requests are made.  
  
## CRecordsets  
 **SQLAllocStmt**, **SQLPrepare**, **SQLExecute** \(For **Open** and **Requery**\), **SQLExecDirect** \(for update operations\), **SQLFreeStmt** must be supported.  **SQLNumResultCols** and **SQLDescribeCol** will be called on the results set at various times.  
  
 **SQLSetParam** is used extensively for binding parameter data and **DATA\_AT\_EXEC** functionality.  
  
 **SQLBindCol** is used extensively to register output Column data storage locations with ODBC.  
  
 Two **SQLGetData** calls are used to retrieve **SQL\_LONG\_VARCHAR** and **SQL\_LONG\_VARBINARY** data.  The first call attempts to find the total length of the column value by calling **SQLGetData** with cbMaxValue of 0, but with a valid pcbValue.  If pcbValue holds **SQL\_NO\_TOTAL**, an exception is thrown.  Otherwise, an `HGLOBAL` is allocated, and another **SQLGetData** call made to retrieve the entire result.  
  
## Mise à jour  
 If pessimistic locking is requested, **SQLGetInfo SQL\_LOCK\_TYPES** will be queried.  If **SQL\_LCK\_EXCLUSIVE** is not supported, an exception will be thrown.  
  
 Attempts to update a `CRecordset` \(**snapshot** or **dynaset**\) will cause a second **HSTMT** to be allocated.  For drivers that do not support second **HSTMT**, the cursor library will simulate this functionality.  Unfortunately, this may sometimes mean forcing the current query on the first **HSTMT** to completion before processing the second **HSTMT**'s request.  
  
 **SQLFreeStmt SQL\_CLOSE** and **SQL\_RESET\_PARAMS** and **SQLGetCursorName** will be called during update operations.  
  
 If there are **CLongBinarys** in the **outputColumns**, ODBC's **DATA\_AT\_EXEC** functionality must be supported.  This includes returning **SQL\_NEED\_DATA** from **SQLExecDirect**, **SQLParamData** and **SQLPutData**.  
  
 **SQLRowCount** is called after executing to verify that only 1 record was updated by the **SQLExecDirect**.  
  
## ForwardOnly Cursors  
 Only **SQLFetch** is required for the **Move** operations.  Note that **forwardOnly** cursors do not support updates.  
  
## Snapshot Cursors  
 Snapshot functionality requires **SQLExtendedFetch** support.  As noted above, the ODBC cursor library will detect when a driver does not support **SQLExtendedFetch**, and provide the necessary support itself.  
  
 **SQLGetInfo**, **SQL\_SCROLL\_OPTIONS** must support **SQL\_SO\_STATIC**.  
  
## Dynaset Cursors  
 Below is the minimum support required to open a dynaset:  
  
 **SQLGetInfo**, **SQL\_ODBC\_VER** must return \> "01".  
  
 **SQLGetInfo**, **SQL\_SCROLL\_OPTIONS** must support **SQL\_SO\_KEYSET\_DRIVEN**.  
  
 **SQLGetInfo**, **SQL\_ROW\_UPDATES** must return "Y".  
  
 **SQLGetInfo**, **SQL\_POSITIONED\_UPDATES** must support **SQL\_PS\_POSITIONED\_DELETE** and **SQL\_PS\_POSITIONED\_UPDATE**.  
  
 In addition, if pessimistic locking is requested, a call to **SQLSetPos** with irow 1, fRefresh FALSE and fLock **SQL\_LCK\_EXCLUSIVE** will be made.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)