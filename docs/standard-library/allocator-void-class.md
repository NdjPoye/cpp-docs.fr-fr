---
title: allocator&lt;void&gt;, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: ef8af7f3ea22529eed77e2259add8fcde21fbd57
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt;, classe
Spécialisation de la classe de modèle allocator en type `void` qui définit les types qui sont pertinents dans ce contexte.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```  
  
## <a name="remarks"></a>Notes  
 La classe spécialise explicitement la classe de modèle [allocator](../standard-library/allocator-class.md) pour le type *void.* Ses constructeurs et l’opérateur d’assignation se comportent de la même façon que la classe de modèle, mais elle définit uniquement les types suivants :  
  
- [const_pointer](../standard-library/allocator-class.md#const_pointer).  
  
- [pointer](../standard-library/allocator-class.md#pointer).  
  
- [value_type](../standard-library/allocator-class.md#value_type).  
  
- [rebind](../standard-library/allocator-class.md#rebind), une classe de modèle imbriquée.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




