---
title: "inject_statement | Microsoft Docs"
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
  - "inject_statement"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inject_statement (attribut)"
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inject_statement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Insère son argument en tant que texte source dans l'en\-tête de bibliothèque de types.  
  
## Syntaxe  
  
```  
inject_statement("source_text")  
```  
  
#### Paramètres  
 `source_text`  
 Texte source à insérer dans le fichier d'en\-tête de bibliothèque de types.  
  
## Notes  
 Le texte est placé au début de la déclaration d'espace de noms qui encapsule le contenu de la bibliothèque de types dans le fichier d'en\-tête.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)