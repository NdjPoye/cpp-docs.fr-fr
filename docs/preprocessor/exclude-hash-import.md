---
title: "exclude (#import) | Microsoft Docs"
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
  - "exclude"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "exclude (attribut)"
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exclude (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Exclut des éléments des fichiers d'en\-tête de bibliothèque de types en cours de création.  
  
## Syntaxe  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### Paramètres  
 `Name1`  
 Premier élément à exclure.  
  
 `Name2`  
 Deuxième élément à exclure \(si nécessaire\).  
  
## Notes  
 Les bibliothèques de types peuvent inclure des définitions d'éléments définis dans les en\-têtes système ou dans d'autres bibliothèques de types.  Cet attribut peut prendre un nombre quelconque d'arguments, chacun étant un élément de niveau supérieur de bibliothèque de types à exclure.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)