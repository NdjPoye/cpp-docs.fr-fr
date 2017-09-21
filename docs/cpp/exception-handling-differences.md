---
title: "Diff&#233;rences de gestion des exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++, différences par rapport à la gestion structurée des exceptions"
  - "exceptions, wrapper (classe)"
  - "gestion structurée des exceptions, différences par rapport à la gestion d'exceptions C++"
  - "gestion structurée des exceptions, différences par rapport à la gestion non structurée"
  - "classes wrapper, exception C"
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Diff&#233;rences de gestion des exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La principale différence entre la gestion structurée des exceptions et la gestion des exceptions C\+\+ est que le modèle de gestion des exceptions C\+\+ traite des types, alors que le modèle de gestion structurée des exceptions C traite des exceptions d'un seul type \(plus spécifiquement `unsigned int`\).  Autrement dit, les exceptions C sont identifiées par une valeur entière non signée, tandis que les exceptions C\+\+ sont identifiées par le type de données.  Lorsqu'une exception est levée en C, chaque gestionnaire possible exécute un filtre qui examine le contexte d'exception C et détermine s'il faut accepter l'exception, la passer à un autre gestionnaire ou l'ignorer.  Lorsqu'une exception est levée en C\+\+, elle peut être de n'importe quelle type.  
  
 Une deuxième différence est que le modèle de gestion structurée des exceptions C est « asynchrone », car les exceptions se produisent de manière secondaire par rapport au flux de contrôle normal.  Le mécanisme de gestion des exceptions C\+\+ est entièrement « synchrone », ce qui signifie que les exceptions se produisent uniquement lorsqu'elles sont levées.  
  
 Si une exception C est levée dans un programme C\+\+, elle peut être gérée par un gestionnaire d'exceptions structuré avec son filtre associé ou par un gestionnaire **catch** C\+\+ , selon celui qui est dynamiquement le plus proche du contexte d'exception.  Par exemple, le programme C\+\+ suivant lève une exception C dans un contexte **try** C\+\+ :  
  
## Exemple  
  
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
  
  **In finally.**  
**Caught a C exception.**   
##  <a name="_core_c_exception_wrapper_class"></a> Classe wrapper d'exception C  
 Dans un exemple simple comme celui\-ci, l'exception C peut être interceptée uniquement par un gestionnaire **catch** de sélection \(**...**\).  Aucune information sur le type ou la nature de l'exception n'est communiquée au gestionnaire.  Bien que cette méthode fonctionne, vous devez parfois définir une transformation entre les deux modèles de gestion des exceptions afin que chaque exception C soit associée à une classe spécifique.  Pour cela, vous pouvez définir une classe « wrapper » d'exception C, qui peut être utilisée ou dont il est possible de dériver pour attribuer un type de classe spécifique à l'exception C.  Ainsi, chaque exception C peut être gérée par un gestionnaire **catch** C\+\+ plus séparément que dans l'exemple précédent.  
  
 Votre classe wrapper peut avoir une interface constituée de certaines fonctions membres qui déterminent la valeur de l'exception et qui accèdent aux informations de contexte d'exception étendues fournies par le modèle d'exception C.  Vous pouvez également définir un constructeur par défaut et un constructeur qui accepte un argument `unsigned int` \(pour les besoins de la représentation d'exception C sous\-jacente\), ainsi qu'un constructeur de copie de bits.  Voici une implémentation possible d'une classe wrapper d'exception C :  
  
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
  
 Pour utiliser cette classe, vous installez une fonction de traduction d'exception C personnalisée appelée par le mécanisme de gestion des exceptions interne chaque fois qu'une exception C est levée.  Dans votre fonction de traduction, vous pouvez lever n'importe quelle exception typée \(par exemple un type `SE_Exception` ou un type de classe dérivé de `SE_Exception`\) qui peut être interceptée par un gestionnaire **catch** C\+\+ approprié.  La fonction de traduction peut simplement retourner, ce qui signifie qu'elle n'a pas géré l'exception.  Si la fonction de traduction proprement dite lève une exception C, [terminate](../c-runtime-library/reference/terminate-crt.md) est appelée.  
  
 Pour spécifier une fonction de traduction personnalisée, appelez la fonction [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) avec le nom de votre fonction de traduction comme unique argument.  La fonction de traduction que vous écrivez est appelée une fois pour chaque appel de fonction sur la pile qui a des blocs **try**.  Il n'existe aucune fonction de traduction par défaut ; si vous n'en spécifiez aucune en appelant `_set_se_translator`, l'exception C ne peut être interceptée que par un gestionnaire **catch** de sélection.  
  
## Exemple  
 Par exemple, le code suivant installe une fonction de traduction personnalisée, puis lève une exception C qui est encapsulée par la classe `SE_Exception` :  
  
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
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**  
**nSE \= 0xc0000094**   
## Voir aussi  
 [Mélange d'exceptions C \(structurées\) et d'exceptions C\+\+](../cpp/mixing-c-structured-and-cpp-exceptions.md)