---
title: "no_implementation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_implementation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_implementation (attribut)"
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# no_implementation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Supprime la génération de l'en\-tête .tli, qui contient les implémentations des fonctions membres de wrapper.  
  
## Syntaxe  
  
```  
no_implementation  
```  
  
## Notes  
 Si cet attribut est spécifié, l'en\-tête .tlh, avec les déclarations pour exposer les éléments de bibliothèque de types, sera généré sans instruction `#include` pour inclure le fichier d'en\-tête .tli.  
  
 Cet attribut est utilisé conjointement avec l'attribut [implementation\_only](../preprocessor/implementation-only.md).  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)