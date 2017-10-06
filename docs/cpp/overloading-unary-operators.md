---
title: "Surcharge des opérateurs unaires | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9ec200fecdebb1c39929882c6fbe4ad09eddc812
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="overloading-unary-operators"></a>Surcharge des opérateurs unaires
Les opérateurs unaires qui peuvent être surchargés sont les suivants :  
  
1.  `!`([NOT logique](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&`([d’adresse](../cpp/address-of-operator-amp.md))  
  
3.  `~`([complément](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*`([déréférencement de pointeur](../cpp/indirection-operator-star.md))  
  
5.  `+`([plus unaire](../cpp/additive-operators-plus-and.md))  
  
6.  `-`([négation unaire](../cpp/additive-operators-plus-and.md))  
  
7.  `++`([incrément](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--`([décrémenter](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. opérateurs de conversion  
  
 L’incrément suffixé et opérateurs de décrémentation (`++` et ** -- **) sont traités séparément dans [incrémenter ou décrémenter](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Les opérateurs de conversion sont également abordées dans une rubrique distincte ; consultez [des Conversions de types définis par l’utilisateur](../cpp/user-defined-type-conversions-cpp.md).  
  
 Les règles suivantes s'appliquent à tous les autres opérateurs unaires. Pour déclarer une fonction d'opérateur unaire en tant que membre non statique, vous devez la déclarer comme suit :  
  
 `ret-type operator` `op` `()`  
  
 où `ret-type` est le type de retour et `op` est l'un des opérateurs répertoriés dans le tableau précédent.  
  
 Pour déclarer une fonction d'opérateur unaire en tant que fonction globale, vous devez la déclarer comme suit :  
  
 `ret-type operator` `op` (`arg` )  
  
 où `ret-type` et `op` apparaissent tels qu'ils sont décrits pour les fonctions d'opérateur de membre, et `arg` est un argument de type de classe à utiliser.  
  
> [!NOTE]
>  Il n'y a aucune restriction sur les types de retour des opérateurs unaires. Par exemple, il paraîtrait logique pour l'opérateur NOT logique (`!`) de retourner une valeur intégrale, mais cela n'est pas appliqué.  
  
## <a name="see-also"></a>Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)
