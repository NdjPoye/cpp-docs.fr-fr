---
title: "rename (#import) | Microsoft Docs"
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
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "renommer un attribut"
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rename (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Offre une solution de contournement pour les problèmes de collisions de noms.  
  
## Syntaxe  
  
```  
rename("OldName","NewName")  
```  
  
#### Paramètres  
 `OldName`  
 Ancien nom dans la bibliothèque de types.  
  
 `NewName`  
 Nom à utiliser au lieu de l'ancien nom.  
  
## Notes  
 Si cet attribut est spécifié, le compilateur remplace toutes les occurrences de *OldName* dans une bibliothèque de types avec le *NewName* fourni par l'utilisateur dans les fichiers d'en\-tête résultants.  
  
 Cet attribut peut être utilisé lorsqu'un nom de la bibliothèque de types coïncide avec une définition de macro dans les fichiers d'en\-tête du système.  Si cette situation n'est pas résolue, diverses erreurs de syntaxe seront générées, par exemple [Erreur du compilateur C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) et [Erreur du compilateur C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).  
  
> [!NOTE]
>  Le remplacement concerne un nom utilisé dans la bibliothèque de types et pas un nom utilisé dans le fichier d'en\-tête résultant.  
  
 Par exemple, supposons qu'une propriété nommée `MyParent` existe dans une bibliothèque de types et qu'une macro `GetMyParent` est définie dans un fichier d'en\-tête et utilisée avant `#import`.  Étant donné que `GetMyParent` est le nom par défaut d'une fonction wrapper pour la propriété **get** de gestion des erreurs, un conflit de noms se produit.  Pour contourner le problème, utilisez l'attribut suivant dans l'instruction `#import` :  
  
```  
rename("MyParent","MyParentX")  
```  
  
 ce qui renomme le nom `MyParent` dans la bibliothèque de types.  Une tentative de changement du nom du wrapper `GetMyParent` échoue :  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Cela provient du fait que le nom `GetMyParent` se produit uniquement dans le fichier d'en\-tête de bibliothèque de types résultant.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)