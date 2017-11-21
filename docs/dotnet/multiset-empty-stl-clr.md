---
title: multiset::Empty (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: 59ec9cc4-cc72-4082-9ab2-49b49980e681
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289c885269c9c40690e58c33d481e4a4081eda00
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="multisetempty-stlclr"></a>multiset::empty (STL/CLR)
Vérifie l'absence d'éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>Remarques  
 La fonction membre retourne la valeur true pour une séquence contrôlée vide. Elle est équivalente à [multiset::size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)`() == 0`. Il permet de tester si le multiensemble est vide.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/set >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)