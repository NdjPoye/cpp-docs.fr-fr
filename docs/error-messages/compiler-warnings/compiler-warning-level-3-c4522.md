---
title: "Avertissement du compilateur (niveau 3) C4522 | Microsoft Docs"
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
  - "C4522"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4522"
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4522
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : plusieurs opérateurs d'assignation spécifiés  
  
 La classe a plusieurs opérateurs d'assignation d'un même type.  Cet avertissement est fourni à titre d'information ; les constructeurs peuvent être appelés dans votre programme.  
  
 Utilisez le pragma [warning](../../preprocessor/warning.md) pour supprimer cet avertissement.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4522 :  
  
```  
// C4522.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }  
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522  
};  
  
int main() {  
   A o1, o2;  
   o2 = o1;  
   const A o3;  
   o1 = o3;  
}  
```