---
title: "#undef, directive (C/C++) | Microsoft Docs"
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
  - "#undef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#undef (directive)"
  - "préprocesseur, directives"
  - "directive undef (#undef)"
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #undef, directive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime \(élimine\) un nom créé précédemment avec `#define`.  
  
## Syntaxe  
  
```  
  
#undef   
identifier  
  
```  
  
## Notes  
 La directive `#undef` supprime la définition actuelle de *identifier*.  Par conséquent, les occurrences suivantes de *identifier* sont ignorées par le préprocesseur.  Pour supprimer une définition de macro à l'aide de `#undef`, indiquez uniquement l'argument *identifier*  de la macro ; ne fournissez pas de liste de paramètres.  
  
 Vous pouvez également appliquer la directive `#undef` à un identificateur qui n'a aucune définition précédente.  Cela garantit que l'identificateur n'est pas défini.  Le remplacement de macro n'est pas effectué dans des instructions `#undef`.  
  
 La directive `#undef` est généralement combinée avec une directive `#define` pour créer une zone dans un programme source dans lequel un identificateur a une signification spéciale.  Par exemple, une fonction spécifique du programme source peut utiliser des constantes manifestes pour définir les valeurs spécifiques à l'environnement qui n'affectent pas le reste du programme.  La directive `#undef` fonctionne également avec la directive `#if` pour contrôler la compilation conditionnelle du programme source.  Consultez [Les directives \#if, \#elif, \#else et \#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) pour plus d'informations.  
  
 Dans l'exemple suivant, la directive `#undef` supprime des définitions d'une constante symbolique et d'une macro.  Notez que seul l'identificateur de la macro est donné.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Section spécifique à Microsoft**  
  
 Les macros peuvent être supprimées de la ligne de commande avec l'option \/U, suivie des noms de macros à supprimer.  Le fait de publier cette commande équivaut à une séquence d'instructions `#undef` *macro\-name* au début du fichier.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)