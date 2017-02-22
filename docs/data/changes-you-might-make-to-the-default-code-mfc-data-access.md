---
title: "Modifications possibles dans le code par d&#233;faut (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "vues des enregistrements (C++), personnaliser le code par défaut"
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Modifications possibles dans le code par d&#233;faut (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'[Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md) écrit pour vous une classe de recordset qui sélectionne tous les enregistrements dans une table.  Vous souhaiterez souvent modifier ce comportement d'une plusieurs des manières suivantes :  
  
-   Définir un filtre ou un ordre de tri pour le recordset.  Effectuez cette action dans `OnInitialUpdate` une fois l'objet recordset construit mais avant que sa fonction membre **Open** soit appelée.  Pour plus d'informations, consultez [Recordset : filtrage d'enregistrements \(ODBC\)](../data/odbc/recordset-filtering-records-odbc.md) et [Recordset : tri d'enregistrements \(ODBC\)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Paramétrer le recordset.  Spécifiez la valeur réelle du paramètre au moment de l'exécution après le filtre.  Pour plus d'informations, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Passer une chaîne SQL personnalisée à la fonction membre [Open](../Topic/CRecordset::Open.md).  Pour obtenir une description des tâches que vous pouvez accomplir avec cette technique, consultez [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
## Voir aussi  
 [Utilisation d'une vue de l'enregistrement](../data/using-a-record-view-mfc-data-access.md)