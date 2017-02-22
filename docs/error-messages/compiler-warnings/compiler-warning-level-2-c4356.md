---
title: "Avertissement du compilateur (niveau 2) C4356 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4356"
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement du compilateur (niveau 2) C4356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : les données membres static ne peuvent pas être initialisées via une classe dérivée  
  
 L'initialisation d'un membre de données static était incorrecte.  Le compilateur a accepté l'initialisation.  
  
 Cela constitue un changement majeur dans le compilateur Visual C\+\+ .NET 2003.  
  
 Pour obtenir un code qui fonctionne de la même manière dans toutes les versions de Visual C\+\+, initialisez le membre par l'intermédiaire de la classe de base.  
  
 Utilisez le pragma [warning](../../preprocessor/warning.md) pour supprimer cet avertissement.  
  
 L'exemple suivant génère l'erreur C4356 :  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```