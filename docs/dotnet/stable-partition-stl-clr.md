---
title: stable_partition (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stable_partition
dev_langs:
- C++
helpviewer_keywords:
- stable_partition function [STL/CLR]
ms.assetid: b82c194c-ae38-4afb-b255-a95a4c2b3101
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 165a13786bab875a568bc055bc0bb0dc8cf21f35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stablepartition-stlclr"></a>stable_partition (STL/CLR)
Classe les éléments d’une plage en deux ensembles disjoints. Les éléments qui répondent à un prédicat unaire doivent précéder ceux qui n’y répondent pas, et l’ordre relatif des éléments équivalents doit être conservé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Notes  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `stable_partition`. Pour plus d’informations, consultez [stable_partition](../standard-library/algorithm-functions.md#stable_partition).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)