---
title: unique (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unique
dev_langs:
- C++
helpviewer_keywords:
- unique function [STL/CLR]
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 95e4ae3fe883f122f3a806dbcba017a0161c84b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="unique-stlclr"></a>unique (STL/CLR)
Supprime les éléments en double adjacents dans une plage spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Notes  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `unique`. Pour plus d’informations, consultez [unique](../standard-library/algorithm-functions.md#unique).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)