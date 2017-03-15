---
title: "Surcharge des op&#233;rateurs unaires | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur d'incrémentation, surchargés"
  - "opérateurs (C++), unaires"
  - "plus (opérateur)"
  - "surcharge de l'opérateur de déréférencement de pointeur"
  - "opérateurs unaires redéfinissables"
  - "opérateurs unaires"
  - "opérateurs unaires, moins"
  - "opérateurs unaires, plus"
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Surcharge des op&#233;rateurs unaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs unaires qui peuvent être surchargés sont les suivants :  
  
1.  `!` \([NOT logique](../cpp/logical-negation-operator-exclpt.md)\)  
  
2.  `&` \([address\-of](../cpp/address-of-operator-amp.md)\)  
  
3.  `~` \([complément](../cpp/one-s-complement-operator-tilde.md)\)  
  
4.  `*` \([déréférencement du pointeur](../cpp/indirection-operator-star.md)\)  
  
5.  `+` \([plus unaire](../cpp/additive-operators-plus-and.md)\)  
  
6.  `-` \([négation unaire](../cpp/additive-operators-plus-and.md)\)  
  
7.  `++` \([incrément](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)\)  
  
8.  `--` \([décrément](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)\)  
  
9. opérateurs de conversion  
  
 Les opérateurs suffixés d'incrémentation et de décrémentation \(`++` et **––**\) sont traités séparément dans [Incrémentation et décrémentation](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Les opérateurs de conversion sont également traités dans une rubrique séparée. Voir [Conversions](../cpp/user-defined-type-conversions-cpp.md).  
  
 Les règles suivantes s'appliquent à tous les autres opérateurs unaires.  Pour déclarer une fonction d'opérateur unaire en tant que membre non statique, vous devez la déclarer comme suit :  
  
 `ret-type operator` `op` `()`  
  
 où `ret-type` est le type de retour et `op` est l'un des opérateurs répertoriés dans le tableau précédent.  
  
 Pour déclarer une fonction d'opérateur unaire en tant que fonction globale, vous devez la déclarer comme suit :  
  
 `ret-type operator` `op` \(`arg` \)  
  
 où `ret-type` et `op` apparaissent tels qu'ils sont décrits pour les fonctions d'opérateur de membre, et `arg` est un argument de type de classe à utiliser.  
  
> [!NOTE]
>  Il n'y a aucune restriction sur les types de retour des opérateurs unaires.  Par exemple, il paraîtrait logique pour l'opérateur NOT logique \(`!`\) de retourner une valeur intégrale, mais cela n'est pas appliqué.  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)