---
title: is_trivially_copyable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- is_trivially_copyable
- std.is_trivially_copyable
- std::is_trivially_copyable
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3e154db9981558eeef6c802a0e9538bdb04a8f9c
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable, classe
Teste si le type peut être copié de façon triviale.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
struct is_trivially_copyable;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` peut être copié de façon triviale. Sinon, sa valeur est false. Les types qui peuvent être copiés de façon triviale ont des opérations de copie, des opérations de déplacement ou des destructeurs non triviaux. En règle générale, une opération de copie est considérée comme triviale si elle peut être implémentée comme copie au niveau du bit. Les types intégrés et les tableaux de types pouvant être copiés de manière triviale peuvent être copiés de manière triviale.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




