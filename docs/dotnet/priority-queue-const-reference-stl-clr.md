---
title: priority_queue::const_reference (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: 53829d08-f875-497a-bb90-655e7f1fd213
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 254fcfbe250a5501286f454b58c3efdda456501b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="priorityqueueconstreference-stlclr"></a>priority_queue::const_reference (STL/CLR)
Type d'une référence constante à un élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit une référence constante à un élément.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_priority_queue_const_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mypriority_queue::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/file d’attente >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::Reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)   
 [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)