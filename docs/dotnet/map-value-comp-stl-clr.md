---
title: Map::value_comp (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::value_comp
dev_langs:
- C++
helpviewer_keywords:
- value_comp member [STL/CLR]
ms.assetid: b0e53052-f3cc-48c8-8e29-1b151c23860a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b67bb629a9de069eb989ee2a1446c58ef5577ef9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="mapvaluecomp-stlclr"></a>map::value_comp (STL/CLR)
Copie le délégué de classement pour les deux valeurs d’éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
value_compare^ value_comp();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne le délégué de classement utilisé pour ordonner la séquence contrôlée. Il permet de comparer deux valeurs d’éléments.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_map_value_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    Mymap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'b', 2),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare([L'a', 1], [L'a', 1]) = False  
compare([L'a', 1], [L'b', 2]) = True  
compare([L'b', 2], [L'a', 1]) = False  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/map >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [carte (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)   
 [map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)