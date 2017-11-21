---
title: accumuler (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::accumulate
dev_langs: C++
helpviewer_keywords: accumulate function [STL/CLR]
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 50334d4468f34afa10639ad18b649c964b126ee4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="accumulate-stlclr"></a>accumulate (STL/CLR)
Calcule la somme de tous les éléments d’une plage spécifiée incluant une valeur initiale en calculant des sommes partielles successives, ou calcule le résultat des résultats partiels successifs obtenus de la même façon en utilisant une opération binaire spécifiée autre que la somme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Remarques  
 Cette fonction comporte comme la fonction de bibliothèque Standard C++ numérique `accumulate`. Pour plus d’informations, consultez [s’accumulent](../standard-library/numeric-functions.md#accumulate).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/numeric >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)