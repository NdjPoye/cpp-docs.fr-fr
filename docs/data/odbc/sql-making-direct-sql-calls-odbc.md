---
title: "SQL&#160;: appels SQL directs (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "appels SQL directs à partir d'ODBC"
  - "ODBC, appels SQL"
  - "appels SQL"
  - "SQL, appeler directement à partir d'ODBC"
  - "SQL, appels directs à partir d'ODBC"
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SQL&#160;: appels SQL directs (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique :  
  
-   quand utiliser les appels SQL directs ;  
  
-   [comment effectuer des appels SQL directs vers la source de données](#_core_making_direct_sql_function_calls).  
  
> [!NOTE]
>  Ces informations s'appliquent aux classes ODBC MFC.  Si vous utilisez les classes DAO MFC, consultez la rubrique « Comparison of Microsoft Jet Database Engine SQL and ANSI SQL » dans l'aide de DAO.  
  
##  <a name="_core_when_to_call_sql_directly"></a> Quand utiliser les appels SQL directs  
 Pour créer des tables, les supprimer ou les modifier, pour créer des index, ou pour effectuer d'autres fonctions SQL qui modifient le schéma de la [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md), vous devez exécuter directement une instruction SQL sur la source de données à l'aide du langage DDL \(Database Definition Language\).  Lorsque vous utilisez un Assistant pour créer un recordset pour une table \(au moment du design\), vous pouvez choisir les colonnes de la table à faire figurer dans le recordset.  En revanche, il n'est pas possible d'utiliser les colonnes que vous\-même ou un autre utilisateur de la source de données avez ajoutées à la table après que votre programme a été compilé.  Les classes de base de données ne prennent pas en charge DDL directement, mais vous pouvez toujours écrire le code permettant de lier dynamiquement une nouvelle colonne à votre recordset, lors de l'exécution.  Pour plus d'informations sur la réalisation de cette liaison, consultez [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Vous pouvez utiliser le SGBD lui\-même pour modifier le schéma, ou tout autre outil permettant d'effectuer les fonctions DDL.  Vous pouvez aussi utiliser les appels de fonction ODBC pour envoyer des instructions SQL, comme l'appel d'une requête prédéfinie \(procédure stockée\) ne retournant pas d'enregistrements.  
  
##  <a name="_core_making_direct_sql_function_calls"></a> Appels directs de fonctions SQL  
 Vous pouvez exécuter directement un appel SQL en utilisant un objet [CDatabase Class](../../mfc/reference/cdatabase-class.md).  Définissez la chaîne de votre instruction SQL \(généralement dans une chaîne `CString`\) et passez\-la à la fonction membre [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) de votre objet `CDatabase`.  Si vous utilisez les appels de fonction ODBC pour transmettre une instruction SQL qui retourne normalement des enregistrements, les enregistrements sont ignorés.  
  
## Voir aussi  
 [SQL](../../data/odbc/sql.md)