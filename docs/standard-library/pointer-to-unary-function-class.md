---
title: "pointer_to_unary_function, classe | Microsoft Docs"
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
  - "xfunctional/std::pointer_to_unary_function"
  - "pointer_to_unary_function"
  - "std.pointer_to_unary_function"
  - "std::pointer_to_unary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_to_unary_function (classe)"
  - "pointer_to_unary_function (fonction)"
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_to_unary_function, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit un pointeur fonction unaire en une fonction unaire adaptable.  
  
## Syntaxe  
  
```  
template<class Arg, class Result>  
class pointer_to_unary_function  
    : public unary_function<Arg, Result>   
    {  
    public:  
        explicit pointer_to_unary_function(  
            Result (*_pfunc)(Arg)  
        );  
        Result operator()(  
            Arg _Left  
        ) const;  
    };  
```  
  
#### Paramètres  
 `_pfunc`  
 La fonction binaire à convertir.  
  
 `_Left`  
 L'objet que la *\*\_pfunc* appelle.  
  
## Valeur de retour  
 La classe de modèle stocke une copie de **\_pfunc**.  Il définit sa fonction membre `operator()` pour retourner \(\***\_pfunc**\)\(\_*Left*\).  
  
## Notes  
 Un pointeur de fonction unaire est une fonction objet et peut être passé à n'importe quel algorithme de la Standard Template Library qui attend une fonction unaire comme paramètre, mais il n'est pas adaptable.  Pour l'utiliser avec un adaptateur, telles que lui lier une valeur ou l'utiliser avec un inverseur, il doit être fourni avec des types imbriqués **argument\_type** et **result\_type** qui rendent une telle adaptation possible.  La conversion par `pointer_to_unary_function` autorise les adaptateurs de fonction à fonctionner avec les pointeurs fonction binaires.  
  
## Exemple  
 Le constructeur de `pointer_to_unary_function` est rarement utilisé directement.  Consultez la fonction d'assistance [ptr\_fun](../Topic/ptr_fun%20Function.md) pour obtenir un exemple de la façon dont déclarer et utiliser l'attribut d'adaptateur `pointer_to_unary_function`.  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)