---
title: "END_ACCESSOR_MAP | Microsoft Docs"
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
  - "END_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR_MAP (macro)"
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# END_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque la fin des entrées de mappage de paramètres.  
  
## Syntaxe  
  
```  
  
END_ACCESSOR_MAP( )  
  
```  
  
## Notes  
 Pour plusieurs accesseurs sur un ensemble de lignes, vous devez spécifier `BEGIN_ACCESSOR_MAP` et utiliser la macro d'`BEGIN_ACCESSOR` pour chaque accesseur individuel.  La macro `BEGIN_ACCESSOR` est terminée avec la macro `END_ACCESSOR`.  La macro `BEGIN_ACCESSOR_MAP` est terminée avec la macro `END_ACCESSOR_MAP`.  
  
## Exemple  
 Voir le [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)