---
title: bad_alloc, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::bad_alloc
- new/std:bad_alloc
- bad_alloc
- std.bad_alloc
dev_langs:
- C++
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3d42ce374744f446185466f65df77a38ebcdbfd4
ms.lasthandoff: 02/24/2017

---
# <a name="badalloc-class"></a>bad_alloc, classe
La classe décrit une exception levée pour indiquer qu'une demande d'allocation n'a pas réussi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par **what** est une chaîne C définie par l’implémentation. Aucune des fonctions membres ne lève d'exception.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<new>  
  
 **Espace de noms :** std  
  
## <a name="example"></a>Exemple  
  
```cpp  
// bad_alloc.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
using namespace std;  
  
int main() {  
   char* ptr;  
   try {  
      ptr = new char[(~unsigned int((int)0)/2) - 1];  
      delete[] ptr;  
   }  
   catch( bad_alloc &ba) {  
      cout << ba.what( ) << endl;  
   }  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
bad allocation  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<new>  
  
## <a name="see-also"></a>Voir aussi
 [exception, classe](../standard-library/exception-class.md)  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


