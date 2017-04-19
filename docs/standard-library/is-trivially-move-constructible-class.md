---
title: is_trivially_move_constructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_move_constructible
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: bfcd131b706f68b6cea38880c3c7fcd49527bba4
ms.lasthandoff: 02/24/2017

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
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




