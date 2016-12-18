---
title: "mem_fun_ref_t, classe | Microsoft Docs"
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
  - "xfunctional/std::mem_fun_ref_t"
  - "mem_fun_ref_t"
  - "std.mem_fun_ref_t"
  - "std::mem_fun_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_ref_t (classe)"
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mem_fun_ref_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe d'adaptateur qui permet à une fonction membre **non\_const** qui ne prend pas d'arguments d'être appelée comme objet fonction unaire une fois initialisée avec un argument de référence.  
  
## Syntaxe  
  
```  
template<class Result, class Type>  
   class mem_fun_ref_t : public unary_function<Type, Result> {  
      explicit mem_fun_ref_t(  
         Result ( Type::*_Pm )( )   
      );  
      Result operator()( Type& _Left ) const;  
   };  
```  
  
#### Paramètres  
 `_Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en un objet de la fonction.  
  
 `_Left`  
 L'objet que la fonction membre d'`_Pm` est appelée.  
  
## Valeur de retour  
 Une fonction unaire adaptable.  
  
## Notes  
 La classe de modèle stocke une copie d'`_Pm`, qui doit être un pointeur vers une fonction membre de la classe **Type**, dans un objet de membre privée.  Il définit sa fonction membre `operator()` comme retourner \(**\_Left**. \* `_Pm`\) \( \).  
  
## Exemple  
 Le constructeur d'`mem_fun_ref_t` n'est généralement pas utilisé directement ; la fonction d'assistance `mem_fun_ref` permet d'ajuster les fonctions de membre.  Voir le [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) pour obtenir un exemple de l'utilisation des adaptateurs de fonction membre.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)