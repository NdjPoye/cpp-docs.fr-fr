---
title: "Erreur du compilateur C2659 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2659"
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : fonction comme opérande gauche  
  
 Une fonction se trouvait sur le côté gauche de l'opérateur spécifié.  En règle générale, cette erreur est due au fait que le compilateur a analysé l'identificateur situé à gauche de l'opérateur en tant que fonction alors que le développeur le destinait à être une variable.  Pour plus d'informations, consultez l'article [Most vexing parse](http://en.wikipedia.org/wiki/Most_vexing_parse) sur Wikipedia.  Cet exemple montre une déclaration de fonction et une définition de variable qui sont faciles à confondre :  
  
```  
// C2659a.cpp  
// Compile using: cl /W4 /EHsc C2659a.cpp  
#include <string>  
using namespace std;  
  
int main()   
{  
   string string1(); // string1 is a function returning string  
   string string2{}; // string2 is a string initialized to empty   
  
   string1 = "String 1"; // C2659  
   string2 = "String 2";  
}  
```  
  
 Pour résoudre ce problème, modifiez la déclaration de l'identificateur afin qu'il ne soit pas analysé comme une déclaration de fonction.  
  
 L'erreur C2659 peut également se produire lorsque la fonction comporte un type qui ne peut pas être utilisé dans l'expression à gauche de l'opérateur spécifié.  Cet exemple génère l'erreur C2659 lorsque le code assigne un pointeur de fonction à une fonction :  
  
```  
// C2659b.cpp  
// Compile using: cl /W4 /EHsc C2659b.cpp  
int func0(void) { return 42; }  
int (*func1)(void);  
  
int main()  
{  
   func1 = func0;  
   func0 = func1; // C2659  
}  
```