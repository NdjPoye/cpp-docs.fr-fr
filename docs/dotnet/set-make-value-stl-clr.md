---
title: Set::make_value (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::make_value
dev_langs:
- C++
helpviewer_keywords:
- make_value member [STL/CLR]
ms.assetid: 2f71515e-7de1-4139-a68e-72ff2a96aa4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9c881a0d7986a628778c63a6a954938db7b8945d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="setmakevalue-stlclr"></a>set::make_value (STL/CLR)
Construit un objet de valeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static value_type make_value(key_type key);  
```  
  
#### <a name="parameters"></a>Paramètres  
 clé  
 Valeur de clé à utiliser.  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne un `value_type` objet dont la clé est `key`. Il permet de composer un objet pouvant être utilisé avec plusieurs autres fonctions membres.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_set_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(Myset::make_value(L'a'));   
    c1.insert(Myset::make_value(L'b'));   
    c1.insert(Myset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Myset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/set >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [Set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Set::KEY_TYPE (STL/CLR)](../dotnet/set-key-type-stl-clr.md)   
 [set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)