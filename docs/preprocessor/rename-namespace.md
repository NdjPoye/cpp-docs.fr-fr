---
title: "rename_namespace | Microsoft Docs"
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
  - "rename_namespace"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "rename_namespace (attribut)"
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rename_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Renomme l'espace de noms qui contient le contenu de la bibliothèque de types.  
  
## Syntaxe  
  
```  
rename_namespace("NewName")  
```  
  
#### Paramètres  
 `NewName`  
 Nom du nouvel espace de noms.  
  
## Notes  
 Il accepte un argument unique, *NewName*, qui spécifie le nouveau nom de l'espace de noms.  
  
 Pour supprimer l'espace de noms, utilisez l'attribut [no\_namespace](../preprocessor/no-namespace.md) à la place.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)