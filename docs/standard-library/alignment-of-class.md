---
title: alignment_of, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- alignment_of
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: dee638b0260deff1d8701353c7119fc1b0082685
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="alignmentof-class"></a>alignment_of, classe
Obtient l'alignement du type spécifié. Ce struct est implémenté en termes d’[alignof](../cpp/alignof-and-alignas-cpp.md). Utilisez `alignof` directement quand vous devez simplement interroger une valeur d'alignement. Utilisez alignment_of quand vous avez besoin d’une constante intégrale, par exemple lors de la répartition d’étiquettes.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct alignment_of;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 La requête de type contient la valeur de l'alignement du type `Ty`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [aligned_storage, classe](../standard-library/aligned-storage-class.md)

