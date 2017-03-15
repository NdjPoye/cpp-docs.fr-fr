---
title: "Transaction (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bases de données (C++), transactions"
  - "ODBC (C++), transactions"
  - "ODBC (recordsets C++), transactions"
  - "ODBC (recordsets C++), mettre à jour"
  - "recordsets (C++), transactions"
  - "recordsets (C++), mettre à jour"
  - "transactions (C++), classes ODBC MFC"
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Transaction (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Une transaction constitue une façon de regrouper une série de mises à jour dans une [source de données](../../data/odbc/data-source-odbc.md) de manière à ce qu'elles soient toutes validées en même temps, ou qu'aucune ne soit validée si vous annulez la transaction.  Si vous n'utilisez pas une transaction, les modifications apportées à la source de données sont validées automatiquement au lieu d'être validées à la demande.  
  
> [!NOTE]
>  Tous les pilotes de base de données ODBC prennent en charge les transactions.  Appelez la fonction membre `CanTransact` de votre objet [CDatabase](../../mfc/reference/cdatabase-class.md) ou [CRecordset](../../mfc/reference/crecordset-class.md) pour savoir si votre pilote prend en charge les transactions pour une base de données particulière.  Sachez cependant que `CanTransact` ne vous indique pas si la source de données assure une prise en charge complète des transactions.  Vous devez également appeler `CDatabase::GetCursorCommitBehavior` et `CDatabase::GetCursorRollbackBehavior` après **CommitTrans** et **Rollback** pour vérifier l'effet de la transaction sur l'objet `CRecordset` ouvert.  
  
 Les appels adressés aux fonctions membres `AddNew` et **Edit** d'un objet `CRecordset` affectent immédiatement la source de données lorsque vous appelez **Update**.  Les appels **Delete** entrent également en vigueur immédiatement.  En revanche, vous pouvez utiliser une transaction composée de plusieurs appels à `AddNew`, **Edit**, **Update** et **Delete**, qui sont exécutés mais pas validés tant que vous n'avez pas explicitement appelé **CommitTrans**.  En établissant une transaction, vous pouvez exécuter une série d'appels de ce type tout en conservant la possibilité de les annuler.  Si une ressource indispensable n'est pas disponible ou que tout autre facteur empêche l'exécution de l'intégralité de la transaction, vous pouvez annuler cette transaction au lieu de la valider.  Dans ce cas, aucune des modifications appartenant à la transaction n'affecte la source de données.  
  
> [!NOTE]
>  Actuellement, la classe `CRecordset` ne prend pas en charge les mises à jour de la source de données si vous avez implémenté l'extraction de lignes en bloc.  Cela signifie que vous ne pouvez exécuter aucun appel à `AddNew`, **Edit**, **Delete** ou **Update**.  Vous pouvez cependant écrire vos propres fonctions pour exécuter des mises à jour, puis appeler ces fonctions à l'intérieur d'une transaction donnée.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Les transactions n'affectent pas seulement votre recordset ; elles affectent également les instructions SQL que vous exécutez directement lorsque vous utilisez le **HDBC** ODBC associé à votre objet `CDatabase` ou un **HSTMT** ODBC basé sur ce **HDBC**.  
  
 Les transactions sont particulièrement utiles lorsque vous devez mettre à jour plusieurs enregistrements à la fois.  Dans ce cas, vous devez éviter qu'une transaction soit seulement à moitié terminée, ce qui peut se produire si une exception est générée avant l'exécution de la dernière mise à jour.  Le groupement de ces mises à jour dans une transaction permet une récupération \(annulation\) après modifications et fait repasser les enregistrements dans l'état qu'ils avaient avant la transaction.  Par exemple, si une banque effectue le virement d'une somme du compte A au compte B, les opérations au débit sur A et au crédit sur B doivent toutes deux réussir pour que le traitement du virement soit correct. Dans le cas contraire, l'intégralité de la transaction se solde par un échec.  
  
 Dans les classes de base de données, vous effectuez des transactions par l'intermédiaire d'objets `CDatabase`.  Un objet `CDatabase` représente une connexion à une source de données et un ou plusieurs recordsets associés à cet objet `CDatabase` agissent sur les tables de la base de données à l'aide des fonctions membres du recordset.  
  
> [!NOTE]
>  Un seul niveau de transactions est pris en charge.  Il est impossible d'imbriquer des transactions et une transaction ne peut pas englober plusieurs objets de base de données.  
  
 Les rubriques ci\-dessous fournissent des informations plus complètes sur les modalités d'exécution des transactions :  
  
-   [Transaction : exécution d'une transaction dans un recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)  
  
-   [Transaction : répercussions des transactions sur les mises à jour \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)