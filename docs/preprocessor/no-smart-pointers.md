---
title: "no_smart_pointers | Microsoft Docs"
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
  - "no_search_pointers"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_smart_pointers (attribut)"
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_smart_pointers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Supprime la création des pointeurs intelligents pour toutes les interfaces dans la bibliothèque de types.  
  
## Syntaxe  
  
```  
no_smart_pointers  
```  
  
## Notes  
 Par défaut, lorsque vous utilisez `#import`, vous obtenez une déclaration de pointeur intelligent pour toutes les interfaces dans la bibliothèque de types.  Ces pointeurs intelligents sont de type [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md).  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)