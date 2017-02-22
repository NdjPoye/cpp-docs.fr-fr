---
title: "Erreur du compilateur C2668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2668"
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur du compilateur C2668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : appel ambigu à une fonction surchargée  
  
 L'appel de fonction surchargée spécifié n'a pas pu être résolu.  Vous pouvez vouloir effectuer un cast explicitement un ou plusieurs des paramètres réels.  
  
 Vous pouvez également obtenir cette erreur en raison de l'utilisation d'un modèle.  Si une fonction membre régulière et une fonction membre modélisée d'une même classe ont la même signature, la fonction modélisée doit figurer en premier.  Il s'agit d'une limitation de l'implémentation actuelle de Visual C\+\+.  
  
 Pour plus d'informations sur le classement partiel des modèles de fonction, consultez l'article Q240869 de la Base de connaissances.  
  
 Si vous générez un projet ATL contenant un objet COM prenant en charge `ISupportErrorInfo`, consultez l'article Q243298 de la Base de connaissances.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2668 :  
  
```  
// C2668.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
  
void func( X, X ){}  
void func( A, B ){}  
D d;  
int main() {  
   func( d, d );   // C2668 D has an A, B, and X   
   func( (X)d, (X)d );   // OK, uses func( X, X )  
}  
```  
  
## Exemple  
 Il est également possible de corriger cette erreur avec une [using declaration](../../cpp/using-declaration.md):  
  
```  
// C2668b.cpp  
// compile with: /EHsc /c  
// C2668 expected  
#include <iostream>  
class TypeA {  
public:  
   TypeA(int value) {}  
};  
  
class TypeB {  
   TypeB(int intValue);  
   TypeB(double dbValue);  
};  
  
class TestCase {  
public:  
   void AssertEqual(long expected, long actual, std::string  
                    conditionExpression = "");  
};  
  
class AppTestCase : public TestCase {  
public:  
   // Uncomment the following line to resolve.  
   // using TestCase::AssertEqual;  
   void AssertEqual(const TypeA expected, const TypeA actual,  
                    std::string conditionExpression = "");  
   void AssertEqual(const TypeB expected, const TypeB actual,  
                    std::string conditionExpression = "");  
};  
  
class MyTestCase : public AppTestCase {  
   void TestSomething() {  
      int actual = 0;  
      AssertEqual(0, actual, "Value");  
   }  
};  
```  
  
## Exemple  
 Cette erreur peut également être due à la mise à conformité du compilateur pour Visual Studio .NET 2003 :conversion ambiguë sur un cast de la constante 0.  
  
 Une conversion sur un cast utilisant la constante 0 est ambiguë puisqu'elle nécessite une conversion au type long et au type void\*.  Pour corriger cette erreur, faites un cast de 0 au type du paramètre de fonction pour lequel il est utilisé afin qu'aucune conversion ne soit effectuée \(ce code sera valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+\).  
  
```  
// C2668c.cpp  
#include "stdio.h"  
void f(long) {  
   printf_s("in f(long)\n");  
}  
void f(void*) {  
   printf_s("in f(void*)\n");  
}  
int main() {  
   f((int)0);   // C2668  
  
   // OK  
   f((long)0);  
   f((void*)0);  
}  
```  
  
## Exemple  
 Cette erreur peut se produire parce que le CRT a maintenant des formes flottante et double de toutes les fonctions mathématiques.  
  
```  
// C2668d.cpp  
#include <math.h>  
int main() {  
   int i = 0;  
   float f;  
   f = cos(i);   // C2668  
   f = cos((float)i);   // OK  
}  
```  
  
## Exemple  
 Cette erreur peut se produire parce que pow\(int, int\) a été supprimé de math.h dans le CRT.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```