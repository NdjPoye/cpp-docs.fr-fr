---
title: bad_alloc, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: new/std::bad_alloc
dev_langs: C++
helpviewer_keywords: bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3bb9257e83eb5c94361bb20ce689eff115817912
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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

