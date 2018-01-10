---
title: adjacent_difference (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::adjacent_difference
dev_langs: C++
helpviewer_keywords: adjacent_difference function
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 97070578c9293eef3fa88e7094e2a90d25ad9ddd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adjacentdifference-stlclr"></a>adjacent_difference (STL/CLR)
Détermine les différences successives entre chaque élément et son prédécesseur au sein d'une plage d'entrée, puis génère les résultats dans une plage de destination ou calcule le résultat d'une procédure généralisée dans laquelle l'opération de différence est remplacée par une autre opération binaire spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Notes  
 Cette fonction comporte comme la fonction de bibliothèque Standard C++ numérique `adjacent_difference`. Pour plus d’informations, consultez [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/numeric >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)