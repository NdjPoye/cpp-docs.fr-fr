---
title: "mem_fun_t, classe | Microsoft Docs"
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
  - "mem_fun_t"
  - "xfunctional/std::mem_fun_t"
  - "std::mem_fun_t"
  - "std.mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_t (classe)"
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mem_fun_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe d'adaptateur qui permet à une fonction membre **non\_const** qui ne prend pas d'arguments d'être appelée comme objet fonction unaire une fois initialisée avec un argument de pointeur.  
  
## Syntaxe  
  
```  
template<class Result, class Type>  
   class mem_fun_t : public unary_function<Type *, Result> {  
      explicit mem_fun_t(Result ( Type::*_Pm )( ) );  
      Result operator()( Type* _Pleft ) const;  
   };  
```  
  
#### Paramètres  
 `_Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en une fonction objet.  
  
 `_Pleft`  
 L'objet que la méthode `_Pm`  a appelé.  
  
## Valeur de retour  
 Une fonction unaire adaptable.  
  
## Notes  
 La classe de modèle stocke une copie de `_Pm`, qui doit être un pointeur vers une fonction membre de classe **Type**, dans un objet membre privé.  Cette option définit sa méthode `operator()` comme retournant \(`_Pleft`\-\>\* `_Pm`\)\( \).  
  
## Exemple  
 Le constructeur de `mem_fun_t` n'est généralement pas utilisé directement; la fonction d'assistance `mem_fun` permet d'ajuster les fonctions membre.  Voir [mem\_fun](../Topic/mem_fun%20Function.md) pour obtenir un exemple de l'utilisation des adaptateurs de fonction membre.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<functional\>](../standard-library/functional.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)