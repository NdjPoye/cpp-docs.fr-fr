---
title: is_trivially_move_constructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17e564e89134a858eabf09b3f208461892da3fb3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible, classe
Teste si le type a un constructeur de déplacement trivial.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct is_trivially_move_constructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur de déplacement trivial. Sinon, sa valeur est false.  
  
 Un constructeur de déplacement pour une classe `Ty` est trivial si :  
  
 il est déclaré implicitement ;  
  
 ses types de paramètres sont équivalents à ceux d'une déclaration implicite ;  
  
 la classe `Ty` n'a aucune fonction virtuelle ;  
  
 la classe `Ty` n'a aucune base virtuelle ;  
  
 la classe n'a aucun membre de données non statique volatile ;  
  
 toutes les bases directes de la classe `Ty` ont des constructeurs de déplacement triviaux ;  
  
 les classes de tous les membres de données non statiques de type de classe ont des constructeurs de déplacement triviaux ;  
  
 les classes de tous les membres de données non statiques de type tableau de classe ont des constructeurs de déplacement triviaux.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



