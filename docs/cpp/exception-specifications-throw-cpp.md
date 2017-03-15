---
title: "Sp&#233;cifications d&#39;exception (throw) (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gestion des exceptions C++, lever des exceptions"
  - "exceptions, spécifications d'exception"
  - "throw (mot clé) (C++), spécifications d'exception"
  - "throw (mot clé) (C++), throw() par rapport à throw(...)"
  - "lever des exceptions, throw (mot clé)"
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cifications d&#39;exception (throw) (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les spécifications d'exceptions sont une fonctionnalité du langage C\+\+ qui est déconseillée dans C\+\+11.  Elles étaient conçues pour fournir des informations résumées concernant les exceptions pouvant être levées à partir d'une fonction, mais dans la pratique elles se sont avérées problématiques.  La seule spécification d'exception qui s'est révélée quelque peu utile est la spécification throw\(\).  Exemple :  
  
```  
void MyFunction(int i) throw();  
```  
  
 indique au compilateur que la fonction ne lève pas d'exception.  Cela revient à utiliser [\_\_declspec \(nothrow\)](../cpp/nothrow-cpp.md).  Son utilisation est considérée comme facultative.  
  
 **C\+\+11\)** Dans la norme ISO C\+\+11, l'opérateur [noexcept](../cpp/noexcept-cpp.md) a été introduit et est pris en charge dans Visual Studio 2015 et versions ultérieures.  Chaque fois que possible, utilisez `noexcept` pour spécifier si une fonction peut lever des exceptions.  
  
 Visual C\+\+ s'éloigne de la norme ISO C\+\+ dans son implémentation des spécifications d'exceptions.  Le tableau suivant résume l'implémentation Visual C\+\+ des spécifications d'exceptions :  
  
|Spécification d'exception|Signification|  
|-------------------------------|-------------------|  
|throw\(\)|La fonction ne lève pas d'exception.  Toutefois, si une exception est levée à partir d'une fonction marquée throw\(\), le compilateur Visual C\+\+ n'effectue pas d'appel inattendu \(consultez [inattendu](../c-runtime-library/reference/unexpected-crt.md) et [inattendu](../Topic/unexpected%20\(%3Cexception%3E\).md) pour plus d'informations\).  Si une fonction est marquée avec throw\(\), le compilateur Visual C\+\+ suppose qu'elle ne lève pas d'exception C\+\+ et il génère le code en conséquence.  En raison des optimisations de code qui peuvent être exécutées par le compilateur C\+\+ \(suite à l'hypothèse selon laquelle la fonction ne lève pas d'exception C\+\+\), si une fonction lève une exception, le programme peut ne pas s'exécuter correctement.|  
|throw\(...\)|La fonction peut lever une exception.|  
|throw\(`type`\)|La fonction peut lever une exception de type `type`.  Toutefois, dans Visual C\+\+ .NET, ceci est interprété comme throw\(...\).  Consultez [Spécificateurs d'exceptions de fonctions](../misc/15-4-function-exception-specifiers.md).|  
  
 Si la gestion des exceptions est utilisée dans une application, il doit exister une ou plusieurs fonctions qui gèrent les exceptions levées.  Toute fonction appelée entre celle qui lève une exception et celle qui gère l'exception doit être capable de lever l'exception.  
  
 Le comportement de levée d'exception d'une fonction dépend des facteurs suivants :  
  
-   si vous compilez la fonction sous C ou C\+\+ ;  
  
-   l'option du compilateur [\/EH](../build/reference/eh-exception-handling-model.md) que vous utilisez ;  
  
-   si vous spécifiez de manière explicite la spécification d'exception.  
  
 Les spécifications d'exceptions explicites ne sont pas autorisées sur les fonctions C.  
  
 Le tableau suivant résume les comportements de levée d'exception d'une fonction :  
  
|Fonction|\/EHsc|\/EHs|\/EHa|\/EHac|  
|--------------|------------|-----------|-----------|------------|  
|Fonction C|throw\(\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|Fonction C\+\+ sans spécification d'exception|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|Fonction C\+\+ avec spécification d'exception throw\(\)|throw\(\)|throw\(\)|throw\(...\)|throw\(...\)|  
|Fonction C\+\+ avec spécification d'exception throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|Fonction C\+\+ avec spécification d'exception throw\(`type`\)|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
  
## Exemple  
  
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
  
  **About to throw 1**  
**in handler**  
**About to throw 1**  
**Caught exception from f4**  
**About to throw 1**  
**in handler**   
## Voir aussi  
 [Instructions try, throw et catch \(C\+\+\)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)