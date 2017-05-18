---
title: pointer_traits, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
dev_langs:
- C++
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
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
ms.openlocfilehash: dbb9a0a8ecd59b76a84ce05b3c239de42be647cb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="pointertraits-struct"></a>pointer_traits, struct
Fournit les informations requises par un objet de la classe de modèle `allocator_traits` pour décrire un allocateur avec le type pointeur `Ptr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
template <class Ptr>
struct pointer_traits;
```  
  
## <a name="remarks"></a>Notes  
 Le pointeur Ptr peut être un pointeur brut du type `Ty *` ou une classe ayant les propriétés suivantes.  
```  
struct Ptr
   { // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj);
   // optional
   };  
```
### <a name="typedefs"></a>Typedefs  
  
|Nom|Description|  
|----------|-----------------|  
|`typedef T2 difference_type`|Le type `T2` est `Ptr::difference_type` si ce type existe. Sinon, le type est `ptrdiff_t`. Si `Ptr` est un pointeur brut, le type est `ptrdiff_t`.|  
|`typedef T1 element_type`|Le type `T1` est `Ptr::element_type` si ce type existe. Sinon, le type est `Ty`. Si `Ptr` est un pointeur brut, le type est `Ty`.|  
|`typedef Ptr pointer`|Le type est `Ptr`.|  
  
### <a name="structs"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|`pointer_traits::rebind`|Tente de convertir le type de pointeur sous-jacent en un type spécifié.|  
  
### <a name="methods"></a>Méthodes  
  
|Nom|Description|  
|----------|-----------------|  
|[pointer_to](#pointer_to)|Convertit une référence arbitraire à un objet de la classe `Ptr`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
##  <a name="pointer_to"></a>  pointer_to  
 Méthode statique qui retourne `Ptr::pointer_to(obj)`, si cette fonction existe. Sinon, il n’est pas possible de convertir une référence arbitraire à un objet de la classe `Ptr`. Si `Ptr` est un pointeur brut, cette méthode retourne `addressof(obj)`.  
  
```cpp  
static pointer pointer_to(element_type& obj);
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<memory>](../standard-library/memory.md)   
 [allocator_traits, classe](../standard-library/allocator-traits-class.md)


