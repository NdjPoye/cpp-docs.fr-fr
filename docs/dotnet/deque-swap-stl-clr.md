---
title: deque::swap (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::deque::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 511e1aa8-3069-43f3-aa77-150f1de1e195
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2f86fa7455edfc29190593660c365e0cfe5ef629
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dequeswap-stlclr"></a>deque::swap (STL/CLR)
Échange le contenu de deux conteneurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void swap(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Paramètres  
 droite  
 Conteneur avec lequel échanger le contenu.  
  
## <a name="remarks"></a>Notes  
 La fonction membre échange les séquences contrôlées entre `*this` et `right`. Cela se fait en temps constant et ne lève aucune exception. Vous l’utiliser comme un moyen rapide de l’échange le contenu de deux conteneurs.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::Assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)