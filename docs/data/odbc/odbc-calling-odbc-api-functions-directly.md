---
title: "ODBC&#160;: appel direct de fonctions API ODBC | Microsoft Docs"
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
  - "API (C++), appeler"
  - "fonctions de catalogue (ODBC)"
  - "fonctions de catalogue (ODBC), appeler"
  - "appels directs d'API ODBC"
  - "ODBC (C++), API (fonctions)"
  - "ODBC (C++), fonctions de catalogue"
  - "ODBC (fonctions API) (C++)"
  - "ODBC (fonctions API) (C++), appeler"
  - "ODBC (classes) (C++), différences par rapport aux ODBC API"
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC&#160;: appel direct de fonctions API ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes de base de données fournissent une interface à une [source de données](../../data/odbc/data-source-odbc.md) plus simple que ODBC.  Par conséquent, les classes n'encapsulent pas toutes les API ODBC.  Vous devez appeler directement les fonctions API ODBC pour toute fonctionnalité en dehors des capacités des classes.  Par exemple, vous devez appeler directement les fonctions de catalogue ODBC \(**::SQLColumns**, **::SQLProcedures**, **::SQLTables**, entre autres\).  
  
> [!NOTE]
>  Les sources de données ODBC sont accessibles via les classes ODBC MFC, comme le décrit cette rubrique, ou via les classes DAO \(Data Access Object\) MFC.  
  
 Pour appeler directement une fonction API ODBC, vous devez procéder de la même façon que lorsque vous effectuez des appels sans la structure.  Les étapes sont les suivantes :  
  
-   Allouez un stockage pour tous les résultats retournés par l'appel.  
  
-   Passez un handle ODBC **HDBC** ou **HSTMT**, selon la signature de paramètre de la fonction.  Utilisez la macro [AFXGetHENV](../Topic/AfxGetHENV.md) pour récupérer le handle ODBC.  
  
     Les variables membres **CDatabase::m\_hdbc** et **CRecordset::m\_hstmt** sont disponibles ; vous ne devez donc pas les allouer, ni les initialiser vous\-même.  
  
-   Appelez peut\-être des fonctions ODBC supplémentaires pour préparer ou suivre l'appel principal.  
  
-   Libérez le stockage lorsque vous avez terminé.  
  
 Pour plus d'informations sur ces étapes, consultez le Kit de développement [ODBC \(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK dans la documentation MSDN.  
  
 En plus de ces étapes, vous devrez également vérifier les valeurs retournées des fonctions, vous assurer que votre programme n'attend pas qu'un appel asynchrone se termine, etc.  Pour simplifier ces dernières étapes, utilisez les macros `AFX_SQL_ASYNC` et `AFX_SQL_SYNC`.  Pour plus d'informations, consultez [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) dans *MFC Reference*.  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)