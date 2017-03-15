---
title: "raw_native_types | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_native_types"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_native_types (attribut)"
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# raw_native_types
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Désactive l'utilisation des classes de prise en charge COM dans les fonctions wrapper de haut niveau et force l'utilisation de types de données de bas niveau à la place.  
  
## Syntaxe  
  
```  
raw_native_types  
```  
  
## Notes  
 Par défaut, les méthodes de gestion des erreurs de niveau supérieur utilisent les classes de prise en charge COM [\_bstr\_t](../cpp/bstr-t-class.md) et [\_variant\_t](../cpp/variant-t-class.md) au lieu des types de données de `BSTR` et **VARIANT** et des pointeurs d'interface COM bruts.  Ces classes encapsulent les détails de l'allocation et de la libération du stockage de mémoire pour ces types de données, et simplifient considérablement le casting de type et les opérations de conversion.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)