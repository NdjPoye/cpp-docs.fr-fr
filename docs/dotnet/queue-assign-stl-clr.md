---
title: Queue::Assign (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: 5bec8a84-9561-43f7-ad7f-f845d0edef41
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fb127496347e39e22b446c84583ad37b75cc025e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="queueassign-stlclr"></a>queue::assign (STL/CLR)
Remplace tous les éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void assign(queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Paramètres  
 droite  
 Adaptateur de conteneur à insérer.  
  
## <a name="remarks"></a>Notes  
 La fonction membre assigne `right.get_container()` au conteneur sous-jacent. Il permet de modifier tout le contenu de la file d’attente.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Myqueue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/file d’attente >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [file d’attente (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)