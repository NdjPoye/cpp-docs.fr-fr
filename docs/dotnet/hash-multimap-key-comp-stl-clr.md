---
title: hash_multimap::key_comp (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::key_comp
dev_langs:
- C++
helpviewer_keywords:
- key_comp member [STL/CLR]
ms.assetid: 221d0bfe-19ad-4c34-9b10-77921be32459
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 10f0860f6eea5fdb3dcb9c6ed8ee2d2454029103
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimapkeycomp-stlclr"></a>hash_multimap::key_comp (STL/CLR)
Copie le délégué de classement pour les deux clés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
key_compare^key_comp();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne le délégué de classement utilisé pour ordonner la séquence contrôlée. Il permet de comparer deux clés.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_hash_multimap_key_comp.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_multimap c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = True  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/hash_map >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::key_compare (STL/CLR)](../dotnet/hash-multimap-key-compare-stl-clr.md)   
 [hash_multimap::key_type (STL/CLR)](../dotnet/hash-multimap-key-type-stl-clr.md)