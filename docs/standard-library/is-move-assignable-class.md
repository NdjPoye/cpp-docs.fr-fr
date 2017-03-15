---
title: is_move_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_move_assignable
- std.is_move_assignable
- std::is_move_assignable
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
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
ms.openlocfilehash: db3e621e4638aab864fa897a6f046f81a6549daa
ms.lasthandoff: 02/24/2017

---
# <a name="ismoveassignable-class"></a>is_move_assignable, classe
Teste si le type peut être assigné par déplacement.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
struct is_move_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Un type est assignable par déplacement si une référence rvalue au type peut être assignée à une référence au type. Le prédicat de type équivaut à `is_assignable<T&, T&&>`. Les types assignables par déplacement incluent les types scalaires référençables et les types de classe qui ont des opérateurs d’assignation par déplacement générés par le compilateur ou définis par l’utilisateur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




