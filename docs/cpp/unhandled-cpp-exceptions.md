---
title: "Les Exceptions C++ non gérées | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handlers, unhandled exceptions
- catch keyword [C++], handler not found
- exceptions, unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 590dc46e5cf761f02ba85dba950c04a2da4df022
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="unhandled-c-exceptions"></a>Exceptions C++ non gérées
Si un gestionnaire correspondant (ou points de suspension **catch** gestionnaire) est introuvable pour l’exception actuelle, prédéfinie `terminate` Runtime est appelée. (Vous pouvez également appeler explicitement `terminate` dans vos gestionnaires.) L'action par défaut de `terminate` est d'appeler `abort`. Si vous souhaitez `terminate` pour appeler une autre fonction dans votre programme avant de quitter l'application, appelez la fonction `set_terminate` avec le nom de la fonction à appeler comme unique argument. Vous pouvez appeler `set_terminate` à tout moment dans votre programme. Le `terminate` routine appelle toujours la dernière fonction donnée comme argument à `set_terminate`.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant lève une exception `char *`, mais ne contient pas de gestionnaire désigné pour intercepter des exceptions de type `char *`. L'appel à `set_terminate` indique à `terminate` d'appeler `term_func`.  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
term_func was called by terminate.  
```  
  
 La fonction `term_func` doit terminer le programme ou le thread actuel, de préférence en appelant `exit`. Si elle ne fait pas cela et revient à la place à son appelant, la fonction `abort` est appelée.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion d’exceptions C++](../cpp/cpp-exception-handling.md)
