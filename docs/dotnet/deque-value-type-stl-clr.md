---
title: deque::Value_type (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::value_type
dev_langs:
- C++
helpviewer_keywords:
- value_type member [STL/CLR]
ms.assetid: c48528c2-966c-4396-be3c-3b9054689dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c1505185ab6f0b96dd5c13bc80ea0de68c7b116c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequevaluetype-stlclr"></a>deque::value_type (STL/CLR)
Type d’un élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Value`.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_value_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::deque<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::const_reference (STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)   
 [deque::reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)