---
title: "Différences de la gestion des exceptions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fff00222aa083bcb392e0d71411bfcf5c0f418
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-differences"></a>Différences de gestion des exceptions
La principale différence entre la gestion structurée des exceptions et la gestion des exceptions C++ est que le modèle de gestion des exceptions C++ traite des types, alors que le modèle de gestion structurée des exceptions C traite des exceptions d'un seul type (plus spécifiquement `unsigned int`). Autrement dit, les exceptions C sont identifiées par une valeur entière non signée, tandis que les exceptions C++ sont identifiées par le type de données. Lorsqu'une exception est levée en C, chaque gestionnaire possible exécute un filtre qui examine le contexte d'exception C et détermine s'il faut accepter l'exception, la passer à un autre gestionnaire ou l'ignorer. Lorsqu'une exception est levée en C++, elle peut être de n'importe quelle type.  
  
 Une deuxième différence est que le modèle de gestion structurée des exceptions C est « asynchrone », car les exceptions se produisent de manière secondaire par rapport au flux de contrôle normal. Le mécanisme de gestion des exceptions C++ est entièrement « synchrone », ce qui signifie que les exceptions se produisent uniquement lorsqu’elles sont levées.  
  
 Si une exception C est levée dans un programme C++, elle peut être gérée par un gestionnaire d’exceptions structuré avec son filtre associé ou en C++ **catch** gestionnaire, plus petite étant retenue dynamiquement plus proche du contexte de l’exception. Par exemple, le programme C++ suivant lève une exception C dans C++ **essayez** contexte :  
  
## <a name="example"></a>Exemple  
  
```  
// exceptions_Exception_Handling_Differences.cpp  
// compile with: /EHa  
#include <iostream>  
  
using namespace std;  
void SEHFunc( void );  
  
int main() {  
   try {  
      SEHFunc();  
   }  
   catch( ... ) {  
      cout << "Caught a C exception."<< endl;  
   }  
}  
  
void SEHFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
   }  
   __finally {  
      cout << "In finally." << endl;  
   }  
}  
```  
  
```Output  
In finally.  
Caught a C exception.  
```  
  
##  <a name="_core_c_exception_wrapper_class"></a>Classe Wrapper d’Exception C  
 Dans un exemple simple comme celui-ci, l’exception C peut être interceptée uniquement par les points de suspension (**...** ) **catch** gestionnaire. Aucune information sur le type ou la nature de l'exception n'est communiquée au gestionnaire. Bien que cette méthode fonctionne, vous devez parfois définir une transformation entre les deux modèles de gestion des exceptions afin que chaque exception C soit associée à une classe spécifique. Pour cela, vous pouvez définir une classe « wrapper » d'exception C, qui peut être utilisée ou dont il est possible de dériver pour attribuer un type de classe spécifique à l'exception C. En procédant ainsi, chaque exception C peut être gérée par une C++ **catch** Gestionnaire plus séparément que dans l’exemple précédent.  
  
 Votre classe wrapper peut avoir une interface constituée de certaines fonctions membres qui déterminent la valeur de l'exception et qui accèdent aux informations de contexte d'exception étendues fournies par le modèle d'exception C. Vous pouvez également définir un constructeur par défaut et un constructeur qui accepte un argument `unsigned int` (pour les besoins de la représentation d'exception C sous-jacente), ainsi qu'un constructeur de copie de bits. Voici une implémentation possible d'une classe wrapper d'exception C :  
  
```  
// exceptions_Exception_Handling_Differences2.cpp  
// compile with: /c  
class SE_Exception {  
private:  
   SE_Exception() {}  
   SE_Exception( SE_Exception& ) {}  
   unsigned int nSE;  
public:  
   SE_Exception( unsigned int n ) : nSE( n ) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() {  
      return nSE;  
   }  
};  
  
```  
  
 Pour utiliser cette classe, vous installez une fonction de traduction d'exception C personnalisée appelée par le mécanisme de gestion des exceptions interne chaque fois qu'une exception C est levée. Dans votre fonction de traduction, vous pouvez lever n’importe quelle exception typée (par exemple un `SE_Exception` type ou un type de classe dérivée de `SE_Exception`) qui peut être interceptée par un C++ approprié **catch** gestionnaire. La fonction de traduction peut simplement retourner, ce qui signifie qu'elle n'a pas géré l'exception. Si la fonction de traduction proprement dite lève une exception C, [Terminer](../c-runtime-library/reference/terminate-crt.md) est appelée.  
  
 Pour spécifier une fonction de traduction personnalisée, appelez le [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) fonction portant le nom de votre fonction de traduction comme unique argument. La fonction de traduction que vous écrivez est appelée une fois pour chaque appel de fonction sur la pile a **essayez** blocs. Il n’existe aucune fonction de traduction par défaut ; Si vous ne spécifiez pas une en appelant `_set_se_translator`, l’exception C peut uniquement être interceptée par une ellipse **catch** gestionnaire.  
  
## <a name="example"></a>Exemple  
 Par exemple, le code suivant installe une fonction de traduction personnalisée, puis lève une exception C qui est encapsulée par la classe `SE_Exception` :  
  
```  
// exceptions_Exception_Handling_Differences3.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <eh.h>  
#include <windows.h>  
  
class SE_Exception {  
private:  
   SE_Exception() {}  
   unsigned int nSE;  
  
public:  
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}  
   SE_Exception(unsigned int n) : nSE(n) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() { return nSE; }  
};  
  
void SEFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
    }  
    __finally {  
      printf_s( "In finally\n" );  
   }  
}  
  
void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {  
   printf_s( "In trans_func.\n" );  
   throw SE_Exception( u );  
}  
  
int main() {  
   _set_se_translator( trans_func );  
    try {  
      SEFunc();  
    }  
    catch( SE_Exception e ) {  
      printf_s( "Caught a __try exception with SE_Exception.\n" );  
      printf_s( "nSE = 0x%x\n", e.getSeNumber() );  
    }  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
nSE = 0xc0000094  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mélange d’exceptions C (structurées) et d’exceptions C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)