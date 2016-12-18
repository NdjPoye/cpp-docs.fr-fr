---
title: "return, instruction (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "return"
  - "return_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "return (mot clé) (C++)"
  - "return (mot clé) (C++), syntaxe"
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# return, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Termine l'exécution d'une fonction et retourne le contrôle à la fonction d'appel \(ou au système d'exploitation si vous transférez le contrôle à partir de la fonction `main`\).  L'exécution reprend dans la fonction d'appel au point immédiatement après l'appel.  
  
## Syntaxe  
  
```  
return [expression];  
```  
  
## Notes  
 La clause `expression`, si elle est présente, est convertie dans le type spécifié dans la déclaration de fonction, comme si une initialisation était exécutée.  La conversion du type de l'expression au type `return` de la fonction peut créer des objets temporaires.  Pour plus d'informations sur les circonstances dans lesquelles les objets temporaries sont créés, consultez [Objets temporaires](../cpp/temporary-objects.md).  
  
 La valeur de la clause `expression` est retournée à la fonction d'appel.  Si l'expression est omise, la valeur de retour de la fonction n'est pas définie.  Les constructeurs et les destructeurs, ainsi que les fonctions du type `void`, `` ne peuvent pas spécifier une expression dans l'instruction `return`.  Les fonctions de tous les autres types doivent spécifier une expression dans l'instruction `return`.  
  
 Lorsque l'ordre d'exécution quitte le bloc englobant la définition de fonction, le résultat est le même que si une instruction `return` sans expression avait été exécutée.  Ceci n'est pas valable pour les fonctions déclarées comme retournant une valeur.  
  
 Une fonction peut comporter plusieurs instructions `return`.  
  
 L'exemple suivant utilise une expression avec une instruction `return` pour obtenir la plus grande valeur de deux entiers.  
  
## Exemple  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)