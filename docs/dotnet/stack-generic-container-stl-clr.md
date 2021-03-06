---
title: Stack::generic_container (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::generic_container
dev_langs:
- C++
helpviewer_keywords:
- generic_container member [STL/CLR]
ms.assetid: 00f106c4-2a02-41cd-80de-f413c9355c74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 244d891256b863c38f4f57175aa0d8d71caae359
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="stackgenericcontainer-stlclr"></a>stack::generic_container (STL/CLR)
Le type de l’interface générique pour l’adaptateur de conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef Microsoft::VisualC::StlClr::IStack<Value>  
    generic_container;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit l’interface générique pour cette classe de l’adaptateur de conteneur de modèle.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_stack_generic_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mystack::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/stack >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualC.StlClr.IStack%602>   
 [pile (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)