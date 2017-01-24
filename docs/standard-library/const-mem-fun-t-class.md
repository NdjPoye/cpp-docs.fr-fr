---
title: "const_mem_fun_t, classe | Microsoft Docs"
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
  - "const_mem_fun_t"
  - "std.const_mem_fun_t"
  - "xfunctional/std::const_mem_fun_t"
  - "std::const_mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_t (classe)"
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# const_mem_fun_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe d'adaptateur qui permet à une fonction membre const qui ne prend pas d'arguments d'être appelée comme objet fonction unaire une fois initialisée avec un argument de référence.  
  
## Syntaxe  
  
```  
template<class Result, class Type>  
   class const_mem_fun_t : public unary_function <Type *, Result>   
   {  
   explicit const_mem_fun_t( Result ( Type::* _Pm )( ) const );  
   Result operator()(  
      const Type* _Pleft  
   ) const;  
   };  
```  
  
#### Paramètres  
 `_Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en un objet de la fonction.  
  
 `_Pleft`  
 L'objet que la fonction membre d'`_Pm` est appelée.  
  
## Valeur de retour  
 Une fonction unaire adaptable.  
  
## Notes  
 La classe de modèle stocke une copie d'`_Pm`, qui doit être un pointeur vers une fonction membre de la classe **Type**, dans un objet de membre privée.  Cette option définit la fonction membre `operator()` comme retourner \(`_Pleft`\(\>\* `_Pm`\)\(\) **const**.  
  
## Exemple  
 Le constructeur d'`const_mem_fun_t` n'est généralement pas utilisé directement ; la fonction d'assistance `mem_fun` permet d'ajuster les fonctions de membre.  Voir le [mem\_fun](../Topic/mem_fun%20Function.md) pour obtenir un exemple de l'utilisation des adaptateurs de fonction membre.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)