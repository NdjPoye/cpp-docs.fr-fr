---
title: is_nothrow_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_nothrow_assignable
dev_langs: C++
helpviewer_keywords: is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe32798dc98335dbada12e1914a77e89f0d78a25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable, classe
Teste si une valeur de type `From` peut être assignée au type `To` et si l’assignation est connue comme ne levant pas d’exception.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class To, class From>  
struct is_nothrow_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 Pour  
 Type de l'objet qui reçoit l'assignation.  
  
 From  
 Type de l'objet qui fournit la valeur.  
  
## <a name="remarks"></a>Notes  
 L’expression `declval<To>() = declval<From>()` doit être bien formée et le compilateur doit savoir qu’elle ne lève pas d’exception. `From` et `To` doivent tous deux être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



