---
title: "END_ACCESSOR | Microsoft Docs"
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
  - "END_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_ACCESSOR (macro)"
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# END_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque la fin d'une entrée d'accesseur.  
  
## Syntaxe  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## Notes  
 Pour plusieurs accesseurs sur un ensemble de lignes, vous devez spécifier `BEGIN_ACCESSOR_MAP` et utiliser la macro d' `BEGIN_ACCESSOR` pour chaque accesseur individuel.  La macro `BEGIN_ACCESSOR` est complétée par la macro `END_ACCESSOR`.  La macro `BEGIN_ACCESSOR_MAP` est complétée par la macro `END_ACCESSOR_MAP`.  
  
## Exemple  
 Consultez [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)