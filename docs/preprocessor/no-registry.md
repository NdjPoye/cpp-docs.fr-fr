---
title: "no_registry | Microsoft Docs"
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
  - "no_registry"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_registry (attribut)"
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_registry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`no_registry` indique au compilateur qu'il ne faut pas rechercher dans le Registre les bibliothèques de types importées avec `#import`.  
  
## Syntaxe  
  
```  
  
#import filename no_registry  
```  
  
#### Paramètres  
 *filename*  
 Bibliothèque de types.  
  
## Notes  
 Si une bibliothèque de types référencée est introuvable dans les répertoires Include, la compilation échoue même si la bibliothèque de types est dans le Registre.  `no_registry` se propage à d'autres bibliothèques de types implicitement importées avec `auto_search`.  
  
 Le compilateur ne recherchera jamais dans le Registre les bibliothèques de types qui sont spécifiées par nom de fichier et passées directement à `#import`.  
  
 Lorsque `auto_search` est spécifié, les  `#import` supplémentaires sont générés avec le paramètre `no_registry` de l'`#import` initial \(si la directive `#import` initiale était `no_registry`, un `#import` généré par `auto_search` est également `no_registry`.\)  
  
 `no_registry` est utile si vous souhaitez importer des bibliothèques de types à référence croisée sans que le compilateur risque de trouver une version antérieure du fichier dans le Registre.  `no_registry` est également utile si la bibliothèque de types n'est pas enregistrée.  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)