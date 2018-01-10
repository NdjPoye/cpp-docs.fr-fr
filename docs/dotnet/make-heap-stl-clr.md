---
title: make_heap (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::make_heap
dev_langs: C++
helpviewer_keywords: make_heap function [STL/CLR]
ms.assetid: bc1bed28-7a26-4540-901d-5584cd117ea1
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d9591c8abce5ecfc4cb0b425fe70a3ac9ce5aea7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="makeheap-stlclr"></a>make_heap (STL/CLR)
Convertit les éléments d’une plage spécifiée en un tas, dans lequel le premier élément est le plus grand, et pour lequel un critère de tri peut être spécifié à l’aide d’un prédicat binaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Notes  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `make_heap`. Pour plus d’informations, consultez [make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)