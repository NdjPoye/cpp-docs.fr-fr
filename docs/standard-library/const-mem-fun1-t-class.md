---
title: "const_mem_fun1_t, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.const_mem_fun1_t"
  - "xfunctional/std::const_mem_fun1_t"
  - "std::const_mem_fun1_t"
  - "const_mem_fun1_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun1_t (classe)"
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun1_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe d'adaptateur qui permet à une fonction membre **const** qui prend un seul argument d'être appelée comme une fonction binaire une fois initialisée avec un argument de pointeur.  
  
## Syntaxe  
  
```  
template<class Result, class Type, class Arg>  
   class const_mem_fun1_t  
      : public binary_function<const Type *, Arg, Result>   
   {  
   explicit const_mem_fun1_t( Result ( Type::* _Pm )( Arg ) const );  
   Result operator()(  
      const Type* _Pleft,   
      Arg _Right  
   ) const;  
   };  
```  
  
#### Paramètres  
 `_Pm`  
 Pointeur vers la fonction membre de la classe **Type** à convertir en une fonction objet.  
  
 `_Pleft`  
 L'objet **const** que la fonction membre `_Pm` a appelé.  
  
 `_Right`  
 L'argument qui doit être fourni pour `_Pm`.  
  
## Valeur de retour  
 Une fonction binaire adaptable.  
  
## Notes  
 La classe de modèle stocke une copie de `_Pm`, qui doit être un pointeur vers une fonction membre de classe **Type**, dans un objet membre privé.  Cette option définit la fonction membre `operator()` comme retourneant \(**\_Pleft**\-\>\* *Pm\) \(***Droite**\) **const**.  
  
## Exemple  
 Le constructeur de `const_mem_fun1_t` n'est généralement pas utilisé directement; la fonction d'assistance `mem_fun` permet d'ajuster les fonctions membre.  Voir [mem\_fun](../Topic/mem_fun%20Function.md) pour obtenir un exemple de l'utilisation des adaptateurs de fonction membre.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)