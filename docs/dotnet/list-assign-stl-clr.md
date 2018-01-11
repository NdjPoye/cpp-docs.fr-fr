---
title: List::Assign (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: c5f2b131-d0e1-4188-9d4b-d617280e4032
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e4c5e670b4fca5998a21b8ae3554f31697cb3fac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="listassign-stlclr"></a>list::assign (STL/CLR)
Remplace tous les éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Paramètres  
 count  
 Nombre d’éléments à insérer.  
  
 premier  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 droite  
 Énumération à insérer.  
  
 Val  
 Valeur de l’élément à insérer.  
  
## <a name="remarks"></a>Notes  
 La première fonction membre remplace la séquence contrôlée par une répétition de `count` éléments ayant la valeur `val`. Utilisez-le pour remplir le conteneur avec des éléments dont la même valeur.  
  
 Si `InIt` est de type entier, la deuxième fonction membre comporte comme `assign((size_type)first, (value_type)last)`. Dans le cas contraire, elle remplace la séquence contrôlée par la séquence [`first`, `last`). Utilisez-le pour rendre le contrôlée une copie de la séquence une autre séquence.  
  
 La troisième fonction membre remplace la séquence contrôlée par la séquence de désignée par l’énumérateur `right`. Il permet d’effectuer la séquence contrôlée une copie d’une séquence décrite par l’énumérateur.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/liste >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)