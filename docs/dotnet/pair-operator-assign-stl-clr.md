---
title: pair::operator = (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::operator=
dev_langs: C++
helpviewer_keywords: operator= member [STL/CLR]
ms.assetid: b6228037-914e-4efa-8491-65dbb0e93f61
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 303300ea172d6a750c376a573a4a6477f360fe92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pairoperator-stlclr"></a>pair::operator= (STL/CLR)
Remplace la paire de valeurs stockée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Paramètres  
 droite  
 Paire à copier.  
  
## <a name="remarks"></a>Notes  
 Les copies d’opérateur de membre `right` à l’objet, puis retourne `*this`. Utilisez-le pour remplacer la paire de valeurs stockée avec une copie de la paire de valeurs dans stockée `right`.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 3]  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/utilitaire >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)