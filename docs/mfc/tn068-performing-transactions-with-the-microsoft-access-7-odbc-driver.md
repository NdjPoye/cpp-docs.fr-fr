---
title: "TN068&#160;: ex&#233;cution de transactions avec le pilote ODBC Microsoft&#160;Access&#160;7 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN068"
  - "transactions, appeler BeginTrans"
  - "transactions, Microsoft Access"
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN068&#160;: ex&#233;cution de transactions avec le pilote ODBC Microsoft&#160;Access&#160;7
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 This note describes how to perform transactions when using the MFC ODBC database classes and the Microsoft Access 7.0 ODBC driver included in the Microsoft ODBC Desktop Driver Pack version 3.0.  
  
## Vue d'ensemble  
 If your database application performs transactions, you must be careful to call `CDatabase::BeginTrans` and `CRecordset::Open` in the correct sequence in your application.  The Microsoft Access 7.0 driver uses the Microsoft Jet database engine, and Jet requires that your application not begin a transaction on any database that has an open cursor.  For the MFC ODBC database classes, an open cursor equates to an open `CRecordset` object.  
  
 If you open a recordset before calling **BeginTrans**, you may not see any error messages.  However, any recordset updates your application makes become permanent after calling `CRecordset::Update`, and the updates will not be rolled back by calling **Rollback**.  To avoid this problem, you must call **BeginTrans** first and then open the recordset.  
  
 MFC checks the driver functionality for cursor commit and rollback behavior.  Class `CDatabase` provides two member functions, `GetCursorCommitBehavior` and `GetCursorRollbackBehavior`, to determine the effect of any transaction on your open `CRecordset` object.  For the Microsoft Access 7.0 ODBC driver, these member functions return `SQL_CB_CLOSE` because the Access driver does not support cursor preservation.  Therefore, you must call `CRecordset::Requery` following a **CommitTrans** or **Rollback** operation.  
  
 When you need to perform multiple transactions one after another, you cannot call **Requery** after the first transaction and then start the next one.  You must close the recordset before the next call to **BeginTrans** in order to satisfy Jet's requirement.  This technical note describes two methods of handling this situation:  
  
-   Closing the recordset after each **CommitTrans** or **Rollback** operation.  
  
-   Using the ODBC API function **SQLFreeStmt**.  
  
## Closing the Recordset after each CommitTrans or Rollback Operation  
 Before starting a transaction, make sure the recordset object is closed.  After calling **BeginTrans**, call the recordset's **Open** member function.  Close the recordset immediately after calling **CommitTrans** or **Rollback**.  Note that repeatedly opening and closing the recordset can slow an application's performance.  
  
## Using SQLFreeStmt  
 You can also use the ODBC API function **SQLFreeStmt** to explicitly close the cursor after ending a transaction.  To start another transaction, call **BeginTrans** followed by `CRecordset::Requery`.  When calling **SQLFreeStmt**, you must specify the recordset's HSTMT as the first parameter and **SQL\_CLOSE** as the second parameter.  This method is faster than closing and opening the recordset at the start of every transaction.  The following code demonstrates how to implement this technique:  
  
```  
CMyDatabase db;  
db.Open( "MYDATASOURCE" );  
CMyRecordset rs( &db );  
  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor  
::SQLFreeStmt( rs.m_hstmt, SQL_CLOSE );  
  
// start transaction 2  
db.BeginTrans( );  
  
// now get the result set  
rs.Requery( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  
  
rs.Close( );  
db.Close( );  
```  
  
 Another way to implement this technique is to write a new function, **RequeryWithBeginTrans**, which you can call to start the next transaction after you commit or rollback the first one.  To write such a function, do the following steps:  
  
1.  Copy the code for **CRecordset::Requery\( \)** to the new function.  
  
2.  Add the following line immediately after the call to **SQLFreeStmt**:  
  
     `m_pDatabase->BeginTrans( );`  
  
 Now you can call this function between each pair of transactions:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor, start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  // or Rollback( )  
```  
  
> [!NOTE]
>  Do not use this technique if you need to change the recordset member variables **m\_strFilter** or `m_strSort` between transactions.  In that case, you should close the recordset after each **CommitTrans** or **Rollback** operation.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)