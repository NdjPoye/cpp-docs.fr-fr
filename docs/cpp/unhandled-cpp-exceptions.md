---
title: "Exceptions C++ non g&#233;r&#233;es | Microsoft Docs"
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
  - "gestion d'exceptions C++, exceptions non gérées"
  - "catch (mot clé) (C++), gestionnaire introuvable"
  - "gestionnaires d'événements, exceptions non gérées"
  - "exceptions, non gérées"
  - "exceptions non gérées"
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions C++ non g&#233;r&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si un gestionnaire correspondant \(ou le gestionnaire **catch** de sélection\) est introuvable pour l'exception actuelle, la fonction runtime `terminate` prédéfinie est appelée. \(Vous pouvez également appeler explicitement `terminate` dans vos gestionnaires.\) L'action par défaut de `terminate` est d'appeler `abort`.  Si vous souhaitez `terminate` pour appeler une autre fonction dans votre programme avant de quitter l'application, appelez la fonction `set_terminate` avec le nom de la fonction à appeler comme unique argument.  Vous pouvez appeler `set_terminate` à tout moment dans votre programme.  La routine `terminate` appelle toujours la dernière fonction donnée comme argument à `set_terminate`.  
  
## Exemple  
 L'exemple suivant lève une exception `char *`, mais ne contient pas de gestionnaire désigné pour intercepter des exceptions de type `char *`.  L'appel à `set_terminate` indique à `terminate` d'appeler `term_func`.  
  
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
  
## Sortie  
  
```  
term_func was called by terminate.  
```  
  
 La fonction `term_func` doit terminer le programme ou le thread actuel, de préférence en appelant `exit`.  Si elle ne fait pas cela et revient à la place à son appelant, la fonction `abort` est appelée.  
  
## Voir aussi  
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)