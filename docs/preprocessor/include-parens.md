---
title: "include() | Microsoft Docs"
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
  - "include()"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include() (attribut)"
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Désactive l'exclusion automatique.  
  
## Syntaxe  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### Paramètres  
 `Name1`  
 Premier élément à inclure de force.  
  
 `Name2`  
 Deuxième élément à inclure de force \(si nécessaire\).  
  
## Notes  
 Les bibliothèques de types peuvent inclure des définitions d'éléments définis dans les en\-têtes système ou dans d'autres bibliothèques de types.  `#import` tente d'éviter les erreurs de définitions multiples en excluant automatiquement ces éléments.  Si des éléments ont été exclus, comme indiqué dans [Avertissement du compilateur \(niveau 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) alors qu'ils ne devaient pas l'être, cet attribut peut être utilisé pour désactiver l'exclusion automatique.  Cet attribut peut comprendre n'importe quel nombre d'arguments, chacun portant le nom de l'élément bibliothèque\-types à inclure.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)