---
title: is_trivially_move_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3f4f27b070a607db4a9ed6929ded346a1be76685
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable, classe
Teste si le type a un opérateur d'assignation de déplacement trivial.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un opérateur d'assignation de déplacement trivial. Sinon, sa valeur est false.  
  
 Un opérateur d'assignation de déplacement pour une classe `Ty` est trivial si :  
  
 il est fourni implicitement ;  
  
 la classe `Ty` n'a aucune fonction virtuelle ;  
  
 la classe `Ty` n'a aucune base virtuelle ;  
  
 les classes de tous les membres de données non statiques de type classe possèdent des opérateurs d'assignation de déplacement triviaux ;  
  
 les classes de tous les membres de données non statiques de type tableau de classe possèdent des opérateurs d'assignation de déplacement triviaux.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




