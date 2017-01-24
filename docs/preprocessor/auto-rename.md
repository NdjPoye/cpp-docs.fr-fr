---
title: "auto_rename | Microsoft Docs"
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
  - "auto_rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "auto_rename (attribut)"
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# auto_rename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Renomme des mots réservés C\+\+ en ajoutant deux traits de soulignement \(\_\_\) au nom de variable pour résoudre les conflits potentiels entre les noms.  
  
## Syntaxe  
  
```  
auto_rename  
```  
  
## Notes  
 Cet attribut est utilisé lors de l'importation d'une bibliothèque de types qui utilise un ou plusieurs mots réservés C\+\+ \(mots clés ou macros\) comme noms de variables.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)