---
title: "const_mem_fun_ref_t, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::const_mem_fun_ref_t"
  - "const_mem_fun_ref_t"
  - "std.const_mem_fun_ref_t"
  - "xfunctional/std::const_mem_fun_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_ref_t (classe)"
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun_ref_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe d'adaptateur qui permet à une méthode **const** qui ne prend pas d'arguments d'être appelée comme un objet fonction unaire une fois initialisée avec un argument de référence.  
  
## Syntaxe  
  
```  
template<class Result, class Type>  
   class const_mem_fun_ref_t  
      : public unary_function<Type, Result>   
   {  
   explicit const_mem_fun_t(Result ( Type::* _Pm)( ) const );  
   Result operator()(  
      const Type& _Left  
   ) const;  
   };  
```  
  
#### Paramètres  
 `_Pm`  
 Pointeur vers la méthode de la classe **Type** à convertir en une fonction objet.  
  
 `_Left`  
 L'objet que la méthode `_Pm`  a appelé.  
  
## Valeur de retour  
 Une fonction unaire adaptable.  
  
## Notes  
 La classe de modèle stocke une copie de `_Pm`, qui doit être un pointeur vers une fonction membre de classe **Type**, dans un objet membre privé.  Il définit sa fonction membre `operator()` pour retourner \(**\_Left**.\* `_Pm`\)\(\) **const**.  
  
## Exemple  
 Le constructeur de `const_mem_fun_ref_t` n'est généralement pas utilisé directement; la fonction d'assistance `mem_fun_ref` permet d'ajuster les fonctions membres.  Voir [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) pour obtenir un exemple de l'utilisation des adaptateurs de fonction membre.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)