---
title: copie (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::copy
dev_langs: C++
helpviewer_keywords: copy function [STL/CLR]
ms.assetid: f6738535-fde6-446e-a797-bf2b457c2bff
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0059c3f3c94f99d3201517f78ea7ecc36211ded4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="copy-stlclr"></a>copy (STL/CLR)
Assigne les valeurs des éléments d'une plage source à une plage de destination, en procédant à une itération via la séquence source d'éléments et en leur assignant de nouvelles positions, du haut vers le bas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
```  
  
## <a name="remarks"></a>Notes  
 Cette fonction comporte comme la fonction de la bibliothèque Standard C++ `copy`. Pour plus d’informations, consultez [copie](http://msdn.microsoft.com/Library/f1fec7da-e01b-40f1-b5bd-6b81e304cae1).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/algorithme >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)