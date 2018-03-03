---
title: Stack::Stack (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::stack
dev_langs:
- C++
helpviewer_keywords:
- stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a59b353bb6ca1dc55933234c68f39f4b76dd16a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stackstack-stlclr"></a>stack::stack (STL/CLR)
Construit un objet d’adaptateur de conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Paramètres  
 droite  
 Objet à copier.  
  
 encapsulé  
 Conteneur encapsulée à utiliser.  
  
## <a name="remarks"></a>Notes  
 Le constructeur :  
  
 `stack();`  
  
 Crée un conteneur encapsulé vide. Il permet de spécifier une séquence contrôlée initiale vide.  
  
 Le constructeur :  
  
 `stack(stack<Value, Container>% right);`  
  
 Crée un conteneur encapsulé est une copie de `right.get_container()`. Il permet de spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par l’objet de pile `right`.  
  
 Le constructeur :  
  
 `stack(stack<Value, Container>^ right);`  
  
 Crée un conteneur encapsulé est une copie de `right->get_container()`. Il permet de spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par l’objet de pile `*right`.  
  
 Le constructeur :  
  
 `explicit stack(container_type% wrapped);`  
  
 utilise le conteneur existant `wrapped` comme conteneur encapsulé. Il permet de construire une pile à partir d’un conteneur existant.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/stack >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [pile (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Stack::Assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [Stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)