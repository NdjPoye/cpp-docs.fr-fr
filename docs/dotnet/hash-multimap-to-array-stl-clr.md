---
title: hash_multimap::to_array (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: a7fe11ba-5a0b-4152-b24d-8b142450863c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4b3a7cfd1a9508305b52f0c8573d13f936876f76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaptoarray-stlclr"></a>hash_multimap::to_array (STL/CLR)
Copie de la séquence contrôlée vers un nouveau tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne un tableau contenant la séquence contrôlée. Il permet d’obtenir une copie de la séquence contrôlée sous forme de tableau.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_hash_multimap_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Myhash_multimap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Myhash_multimap::make_value(L'd', 4));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Myhash_multimap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3] [d 4]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/hash_map >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)