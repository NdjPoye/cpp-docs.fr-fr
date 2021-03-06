---
title: Vector::const_reference (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: c68743cd-5367-46ca-88ae-b90b2f0ecc34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 926e5c763c1e50b6792cce29bfa1ff814cf32777
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="vectorconstreference-stlclr"></a>vector::const_reference (STL/CLR)
Type d'une référence constante à un élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit une référence constante à un élément.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_vector_const_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::vector<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/vector >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [vecteur (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)   
 [vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)