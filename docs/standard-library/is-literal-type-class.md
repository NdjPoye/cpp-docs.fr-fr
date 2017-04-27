---
title: is_literal_type, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_literal_type
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
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
ms.openlocfilehash: 5a89b32e85cc7756f4d420f8eea55b2088a44320
ms.lasthandoff: 02/24/2017

---
# <a name="isliteraltype-class"></a>is_literal_type, classe
Teste si un type peut être utilisé comme variable `constexpr`, ou être construit, utilisé par ou retourné à partir de fonctions `constexpr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
struct is_literal_type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un *type littéral*. Sinon, sa valeur est false. Un type littéral est `void`, un type scalaire, un type référence, un tableau de type littéral ou un type de classe littéral. Un type de classe littéral est un type de classe qui a un destructeur trivial, est un type d’agrégation ou a au moins un constructeur `constexpr` sans déplacement et sans copie, et toutes ses classes de base et données membres non statiques sont des types littéraux non volatiles. Bien que le type d’un littéral soit toujours un type littéral, le concept de type littéral inclut tout ce que le compilateur peut évaluer en tant que `constexpr` au moment de la compilation.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




