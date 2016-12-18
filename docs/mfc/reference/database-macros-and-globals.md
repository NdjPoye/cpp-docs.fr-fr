---
title: "Macros et objet Globals de base de donn&#233;es | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "base de données (globals) (C++)"
  - "macros de base de données (C++)"
  - "fonctions de base de données globales (C++)"
  - "fonctions globales (C++), fonctions de base de données"
  - "macros (C++), base de données MFC"
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Macros et objet Globals de base de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les macros et les variables globales ci\-dessous s'appliquent aux applications de base de données basées sur.  Elles ne sont pas utilisées avec les applications DAO.  
  
 Avant MFC 4,2, les macros `AFX_SQL_ASYNC` et `AFX_SQL_SYNC` ont fourni aux opérations asynchrones la possibilité de produire le temps à d'autres processus.  À compter de MFC 4,2, l'implémentation des macros a changé parce que les classes ODBC MFC utilisées seules les opérations synchrones.  Macro `AFX_ODBC_CALL` constitue une nouveauté de MFC 4,2.  
  
### Les macros de base de données \(C\+\+\)  
  
|||  
|-|-|  
|[AFX\_ODBC\_CALL](../Topic/AFX_ODBC_CALL.md)|Appelle une fonction API ODBC qui renvoie `SQL_STILL_EXECUTING`.  `AFX_ODBC_CALL` appelera à plusieurs reprises la fonction jusqu'à ce qu'il ne renvoie plus `SQL_STILL_EXECUTING`.|  
|[AFX\_SQL\_ASYNC](../Topic/AFX_SQL_ASYNC.md)|appelle `AFX_ODBC_CALL`.|  
|[AFX\_SQL\_SYNC](../Topic/AFX_SQL_SYNC.md)|Appelle une fonction API ODBC qui ne renvoie pas `SQL_STILL_EXECUTING`.|  
  
### base de données \(globals\)  
  
|||  
|-|-|  
|[AfxGetHENV](../Topic/AfxGetHENV.md)|Récupère un handle d'environnement ODBC actuellement utilisée par MFC.  Utilisez ce handle des appels directs ODBC.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)