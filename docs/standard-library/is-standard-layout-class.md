---
title: is_standard_layout, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 41d0472a031904fbb40d381aa6113da17feb3e1b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="isstandardlayout-class"></a>is_standard_layout, classe
Teste si le type est une disposition standard.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct is_standard_layout;
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Ty`|Type à interroger|  
  
## <a name="remarks"></a>Notes  
 Une instance de ce prédicat de type a la valeur true si le type `Ty` est une classe qui a une disposition standard d'objets membres en mémoire. Sinon, sa valeur est false.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




