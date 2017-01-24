---
title: "bad_alloc, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::bad_alloc"
  - "new/std:bad_alloc"
  - "bad_alloc"
  - "std.bad_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_alloc (classe)"
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_alloc, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe décrit une exception levée pour indiquer qu'une demande d'allocation n'a pas réussi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>Remarques  
 La valeur retournée par **que** est une chaîne définie par l’implémentation de C. Aucune des fonctions membres ne lève d'exception.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< nouveau>  
  
 **Namespace :** std  
  
## <a name="example"></a>Exemple  
  
```  
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
 **En-tête :** \< nouveau>  
  
## <a name="see-also"></a>Voir aussi
 [exception (classe)](../standard-library/exception-class1.md)  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

