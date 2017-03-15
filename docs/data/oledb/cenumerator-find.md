---
title: "CEnumerator::Find | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CEnumerator::Find"
  - "ATL::CEnumerator::Find"
  - "ATL.CEnumerator.Find"
  - "CEnumerator.Find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Find (méthode)"
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CEnumerator::Find
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche le nom spécifié parmi les fournisseurs disponibles.  
  
## Syntaxe  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
```  
  
#### Paramètres  
 *szSearchName*  
 \[in\] Nom à rechercher.  
  
## Valeur de retour  
 **true** si le nom est trouvé.  sinon, **false**.  
  
## Notes  
 Les cartes de ce nom au membre de **SOURCES\_NAME** de l'interface [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CEnumerator, classe](../../data/oledb/cenumerator-class.md)