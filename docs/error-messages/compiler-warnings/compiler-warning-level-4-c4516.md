---
title: "Avertissement du compilateur (niveau 4) C4516 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4516"
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 4) C4516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::symbole' : les déclarations d'accès ont été remplacées ; les déclarations using de membres constituent un meilleur choix  
  
 Le comité C\+\+ ANSI a déclaré anachroniques les déclarations d'accès \(modification d'accès d'un membre dans une classe dérivée sans le mot clé [using](../../cpp/using-declaration.md)\).  Les déclarations d'accès peuvent ne plus être prises en charge dans des versions ultérieures de C\+\+.  
  
 L'exemple suivant génère l'erreur C4516 :  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```