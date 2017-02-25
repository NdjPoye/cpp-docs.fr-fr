---
title: "no_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_namespace (attribut)"
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# no_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Indique que le nom de l'espace de noms n'est pas généré par le compilateur.  
  
## Syntaxe  
  
```  
no_namespace  
```  
  
## Notes  
 Le contenu de la bibliothèque de types dans le fichier d'en\-tête `#import` est normalement défini dans un espace de noms.  Le nom de l'espace de noms est spécifié dans l'instruction **library** du fichier IDL d'origine.  Si l'attribut `no_namespace` est spécifié, cet espace de noms n'est pas généré par le compilateur.  
  
 Pour utiliser un nom d'espace de noms différent, employez l'attribut [rename\_namespace](../preprocessor/rename-namespace.md) à la place.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)