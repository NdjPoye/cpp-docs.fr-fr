---
title: "raw_interfaces_only | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_interfaces_only"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_interfaces_only (attribut)"
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# raw_interfaces_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Supprime la génération des fonctions wrapper de gestion d'erreurs et des déclarations [propriété](../cpp/property-cpp.md) qui utilisent ces fonctions wrapper.  
  
## Syntaxe  
  
```  
raw_interfaces_only  
```  
  
## Notes  
 L'attribut `raw_interfaces_only` entraîne également la suppression du préfixe par défaut utilisé dans l'attribution de nom des fonctions qui ne sont pas une propriété.  Normalement, le préfixe est **raw\_**.  Si cet attribut est spécifié, les noms de fonctions proviennent directement de la bibliothèque de types.  
  
 Cet attribut vous permet d'exposer uniquement le contenu de bas niveau de la bibliothèque de types.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)