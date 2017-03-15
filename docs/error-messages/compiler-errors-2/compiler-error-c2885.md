---
title: "Erreur du compilateur C2885 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2885"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2885"
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Erreur du compilateur C2885
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::identificateur' : déclaration using non valide au niveau d'une portée qui n'est pas de classe  
  
 Vous avez mal utilisé une déclaration [using](../../cpp/using-declaration.md).  
  
## Exemple  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : une déclaration `using` pour un type imbriqué n'est désormais plus valide ; vous devez qualifier explicitement chaque référence au type imbriqué, placer le type dans un espace de noms ou créer un typedef.  
  
 L'exemple suivant génère l'erreur C2885 :  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## Exemple  
 Si vous utilisez le mot clé `using` avec un membre de classe, C\+\+ vous impose de définir ce membre à l'intérieur d'une autre classe \(une classe dérivée\).  
  
 L'exemple suivant génère l'erreur C2885 :  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```