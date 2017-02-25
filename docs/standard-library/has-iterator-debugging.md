---
title: "_HAS_ITERATOR_DEBUGGING | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HAS_ITERATOR_DEBUGGING"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HAS_ITERATOR_DEBUGGING"
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _HAS_ITERATOR_DEBUGGING
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit si la fonctionnalité de débogage d'itération est activée dans une version de débogage.  Par défaut, le débogage d'itération est activé.  Pour plus d'informations, consultez [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md).  
  
> [!IMPORTANT]
>  Utilisation `_ITERATOR_DEBUG_LEVEL` de contrôler `_HAS_ITERATOR_DEBUGGING`.  Pour plus d'informations, consultez [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Notes  
 Pour activer le débogage d'itération dans les versions de débogage, affectez **\_HAS\_ITERATOR\_DEBUGGING** à 1 :  
  
```  
#define _HAS_ITERATOR_DEBUGGING 1  
```  
  
 **\_HAS\_ITERATOR\_DEBUGGING** ne peut pas avoir la valeur 1 dans les versions de ventes.  
  
 Pour désactiver le débogage d'itération dans les versions de débogage, affectez **\_HAS\_ITERATOR\_DEBUGGING** à 0 :  
  
```  
#define _HAS_ITERATOR_DEBUGGING 0  
```  
  
## Voir aussi  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md)   
 [Itérateurs vérifiés](../standard-library/checked-iterators.md)   
 [Bibliothèques sécurisées : bibliothèque C\+\+ standard](../standard-library/safe-libraries-cpp-standard-library.md)