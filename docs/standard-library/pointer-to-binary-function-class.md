---
title: "pointer_to_binary_function, classe | Microsoft Docs"
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
  - "std::pointer_to_binary_function"
  - "xfunctional/std::pointer_to_binary_function"
  - "pointer_to_binary_function"
  - "std.pointer_to_binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_binary_function (classe)"
  - "pointer_to_binary_function (fonction)"
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_to_binary_function, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit un pointeur fonction binaire en une fonction binaire adaptable.  
  
## Syntaxe  
  
```  
template<class Arg1, class Arg2, class Result>  
   class pointer_to_binary_function   
   : public binary_function <Arg1, Arg2, Result>   
   {  
   public:  
   explicit pointer_to_binary_function(  
      Result (*_pfunc )( Arg1, Arg2 )   
   );  
   Result operator()(  
      Arg1 _Left,   
      Arg2 _Right  
   ) const;  
   };  
```  
  
#### Paramètres  
 `_pfunc`  
 La fonction binaire à convertir.  
  
 `_Left`  
 L'objet gauche que *le \*\_pfunc* est appelée.  
  
 `_Right`  
 Celle de l'objet que *le \*\_pfunc* est appelée.  
  
## Valeur de retour  
 La classe de modèle stocke une copie de **\_pfunc**.  Il définit sa fonction membre `operator()` comme retourner \(\***\_pfunc**\) \(\_Left, \_Right\).  
  
## Notes  
 Un pointeur fonction binaire est un objet de la fonction et peut être passé à n'importe quel algorithme Standard TEMPLATE bibliothèque qui attend une fonction binaire comme paramètre, mais il n'est pas adaptable.  À utiliser avec un adaptateur, telles que la liaison d'une valeur de est ou l'utiliser avec un inverseur, il doit être fourni avec des types imbriqués **first\_argument\_type**, **second\_argument\_type**, et **result\_type** qui rendent une telle adaptation possible.  La conversion par `pointer_to_binary_function` autorise les adaptateurs de fonction fonctionne avec les pointeurs fonction binaires.  
  
## Exemple  
 Le constructeur d'`pointer_to_binary_function` est souvent utilisé directement.  Consultez la fonction d'assistance [ptr\_fun](../Topic/ptr_fun%20Function.md) pour obtenir un exemple de la façon dont déclarer et utiliser l'attribut d'adaptateur d'`pointer_to_binary_function`.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)