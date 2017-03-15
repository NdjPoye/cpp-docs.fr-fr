---
title: is_trivially_copy_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_copy_assignable
- std.is_trivially_copy_assignable
- std::is_trivially_copy_assignable
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 97935fed1736f111557a0cb86811a86d60505107
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable, classe
Teste si le type a un opérateur d'assignation de copie trivial.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est une classe qui a un opérateur d'assignation de copie trivial. Sinon, sa valeur est false.  
  
 Un constructeur d’affectation d’une classe `T` est trivial s’il est implicitement fourni, si la classe `T` n’a aucune fonction virtuelle, si la classe `T` n’a aucune base virtuelle, si les classes de toutes les données membres non statiques de type classe ont des opérateurs d’assignation triviaux et si les classes de toutes les données membres non statiques de type tableau de classe ont des opérateurs d’assignation triviaux.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




