---
title: "Spécifications d’exception (throw) (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7559bdf725727b79f99ed3bfcd4d6b7301528110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-specifications-throw-noexcept-c"></a>Spécifications d’exception (throw, noexcept) (C++)
Spécifications d’exceptions sont une fonctionnalité du langage C++ qui indiquent l’intention du programmeur sur les types d’exception qui peuvent être propagées par une fonction. Vous pouvez spécifier qu’une fonction peut ou peut ne pas quitte par une exception à l’aide un *spécification d’exception*. Le compilateur peut utiliser ces informations pour optimiser les appels à la fonction, et la fonction d’échappement pour terminer le programme si une exception inattendue. Il existe deux types de spécification d’exception. Le *noexcept spécification* est une nouveauté dans C ++ 11. Il spécifie si l’ensemble des exceptions potentielles qui échappent à la fonction est vide. Le *spécification d’exception dynamiques*, ou `throw(optional_type_list)` spécification, est déconseillée dans C ++ 11 et n'est que partiellement prise en charge par Visual Studio. Cette spécification d’exception a été conçue pour fournir des informations résumées concernant les exceptions pouvant être levées en dehors d’une fonction, mais dans la pratique, il a été trouvé pour poser des problèmes. La spécification d’exception dynamique un qui s’est révélée quelque peu utile a été l’inconditionnel `throw()` spécification. Par exemple, la déclaration de fonction :  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 indique au compilateur que la fonction ne lève pas d'exception. Cela revient à l’aide de [__declspec (nothrow)](../cpp/nothrow-cpp.md). Son utilisation est considérée comme facultative.  
  
Dans la norme ISO C ++ 11 Standard, le [noexcept](../cpp/noexcept-cpp.md) opérateur a été introduit en remplacement. Il est pris en charge dans Visual Studio 2015 et versions ultérieures. Si possible, utilisez un `noexcept` expression pour spécifier si une fonction peut lever des exceptions. Par exemple, utilisez cette déclaration de fonction au lieu de celui illustré ci-dessus :  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Pendant que Visual C++ prend entièrement en charge le `noexcept` expression, il ne respecte pas la norme ISO C++ dans son implémentation de spécifications d’exception dynamiques.  Le tableau suivant résume l'implémentation Visual C++ des spécifications d'exceptions :  
  
|Spécification d'exception|Signification|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|La fonction ne lève pas d'exception. Toutefois, si une exception est levée en dehors d’une fonction marquée `throw()`, le compilateur Visual C++ appelle `std::terminate`, et non `std::unexpected`. Consultez [std::unexpected](../c-runtime-library/reference/unexpected-crt.md) pour plus d’informations. Si une fonction est marquée `noexcept`, `noexcept(true)`, ou `throw()`, le compilateur Visual C++ suppose que la fonction ne lève pas d’exceptions C++ et génère le code en conséquence. Étant donné que les optimisations de code peuvent être effectuées par le compilateur C++ basé sur l’hypothèse que la fonction ne lève pas d’exception C++, si une fonction lève une exception, le programme ne peut pas exécutés correctement.|  
|`noexcept(false)`<br/>`throw(...)`<br/>Aucune spécification|La fonction peut lever une exception de n’importe quel type.|  
|`throw(type)`|La fonction peut lever une exception de type `type`. Dans Visual C++, cette syntaxe est acceptée, mais il est interprété comme `noexcept(false)`.|  
  
 Si la gestion des exceptions sont utilisée dans une application, il doit être une fonction dans la pile des appels qui gère levée des exceptions avant de quitter l’étendue externe d’une fonction marquée `noexcept`, `noexcept(true)`, ou `throw()`. Si aucune fonction appelée entre celle qui lève une exception et celui qui gère l’exception sont spécifiés en tant que `noexcept`, `noexcept(true)`, ou `throw()`, le programme se termine lorsque la fonction noexcept propage l’exception.  
  
 Le comportement d’exception d’une fonction dépend des facteurs suivants :  
  
-   si vous compilez la fonction sous C ou C++ ;  
  
-   Qui [/EH](../build/reference/eh-exception-handling-model.md) option du compilateur que vous utilisez.  
  
-   si vous spécifiez de manière explicite la spécification d'exception.  
  
 Les spécifications d'exceptions explicites ne sont pas autorisées sur les fonctions C. Une fonction C est supposée ne pas pour lever d’exceptions sous **/EHsc**et peut lever des exceptions structurées sous **/EHs**, **/EHa**, ou **/EHac**.  
  
 Le tableau suivant récapitule si une fonction C++ peut lever potentiellement sous différentes du compilateur exceptions options :  
  
|Fonction|/EHsc|/EHs|/EHa|/EHac|  
|--------------|------------|-----------|-----------|------------|  
|Fonction C++ sans spécification d'exception|Oui|Oui|Oui|Oui|  
|Fonction C++ avec `noexcept`, `noexcept(true)`, ou `throw()` spécification d’exception|Non|Non|Oui|Oui|  
|Fonction C++ avec `noexcept(false)`, `throw(...)`, ou `throw(type)` spécification d’exception|Oui|Oui|Oui|Oui|  
  
## <a name="example"></a>Exemple  
  
```cpp  
// exception_specification.cpp  
// compile with: /EHs  
#include <stdio.h>  
  
void handler() {  
   printf_s("in handler\n");  
}  
  
void f1(void) throw(int) {  
   printf_s("About to throw 1\n");  
   if (1)  
      throw 1;  
}  
  
void f5(void) throw() {  
   try {  
      f1();  
   }  
   catch(...) {  
      handler();  
    }  
}  
  
// invalid, doesn't handle the int exception thrown from f1()  
// void f3(void) throw() {  
//   f1();  
// }  
  
void __declspec(nothrow) f2(void) {  
   try {  
      f1();  
   }  
   catch(int) {  
      handler();  
    }  
}  
  
// only valid if compiled without /EHc   
// /EHc means assume extern "C" functions don't throw exceptions  
extern "C" void f4(void);  
void f4(void) {  
   f1();  
}  
  
int main() {  
   f2();  
  
   try {  
      f4();  
   }  
   catch(...) {  
      printf_s("Caught exception from f4\n");  
   }  
   f5();  
}  
```  
  
```Output  
About to throw 1  
in handler  
About to throw 1  
Caught exception from f4  
About to throw 1  
in handler  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions try, throw et catch (C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [Gestion d’exceptions C++](../cpp/cpp-exception-handling.md)