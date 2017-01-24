---
title: "high_method_prefix | Microsoft Docs"
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
  - "high_method_prefix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "high_method_prefix (attribut)"
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# high_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie un préfixe à utiliser pour nommer les propriétés et les méthodes de haut niveau.  
  
## Syntaxe  
  
```  
high_method_prefix("Prefix")  
```  
  
#### Paramètres  
 `Prefix`  
 Préfixe à utiliser.  
  
## Notes  
 Par défaut, les propriétés de gestion des erreurs et les méthodes de niveau supérieur sont exposées par des fonctions membres nommées sans préfixe.  Les noms sont issus de la bibliothèque de types.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)