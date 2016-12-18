---
title: "no_auto_exclude | Microsoft Docs"
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
  - "no_auto_exclude"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_auto_exclude (attribut)"
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_auto_exclude
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Désactive l'exclusion automatique.  
  
## Syntaxe  
  
```  
no_auto_exclude  
```  
  
## Notes  
 Les bibliothèques de types peuvent inclure des définitions d'éléments définis dans les en\-têtes système ou dans d'autres bibliothèques de types.  `#import` tente d'éviter les erreurs de définitions multiples en excluant automatiquement ces éléments.  Une fois cette opération effectuée, l'avertissement [Avertissement du compilateur \(niveau 3\) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) sera émis pour chaque élément à exclure.  Vous pouvez désactiver cette exclusion automatique à l'aide de cet attribut.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)