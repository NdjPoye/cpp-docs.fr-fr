---
title: "_SECURE_SCL | Microsoft Docs"
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
  - "_SECURE_SCL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SECURE_SCL"
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _SECURE_SCL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit si [Itérateurs vérifiés](../standard-library/checked-iterators.md) sont activés.  Si défini à 1, une utilisation non sécurisée d'itérateurs provoque une erreur d'exécution et le programme se termine.  S'il est défini sur 0, les itérateurs vérifiés sont désactivés.  En mode débogage, la valeur par défaut de **\_SECURE\_SCL** est 1, ce qui signifie que les itérateurs vérifiés sont activés.  En mode normal, la valeur par défaut de `_SECURE_SCL` est 0.  
  
> [!IMPORTANT]
>  Utilisez `_ITERATOR_DEBUG_LEVEL` pour contrôler `_SECURE_SCL`.  Pour plus d'informations, consultez [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Notes  
 Pour activer les itérateurs extraits, définissez **\_SECURE\_SCL** à 1 :  
  
```  
#define _SECURE_SCL 1  
```  
  
 Pour désactiver les itérateurs vérifiés, définissez **\_SECURE\_SCL** à 0 :  
  
```  
#define _SECURE_SCL 0  
```  
  
 Pour plus d'informations sur la manière de désactiver les avertissements générés par les itérateurs vérifiés, consultez [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## Voir aussi  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Itérateurs vérifiés](../standard-library/checked-iterators.md)   
 [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md)   
 [Bibliothèques sécurisées : bibliothèque C\+\+ standard](../standard-library/safe-libraries-cpp-standard-library.md)