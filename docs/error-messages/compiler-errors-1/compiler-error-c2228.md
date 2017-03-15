---
title: "Erreur du compilateur C2228 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2228"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2228"
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2228
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la partie gauche de '.identifier' doit avoir un class\/struct\/union  
  
 L’opérande située à gauche du point \(.\) n’est pas une classe, une structure ou une union.  
  
 L’exemple suivant génère l’erreur C2228 :  
  
```  
// C2228.cpp int i; struct S { public: int member; } s, *ps = &s; int main() { i.member = 0;   // C2228 i is not a class type ps.member = 0;  // C2228 ps is a pointer to a structure s.member = 0;   // s is a structure type ps->member = 0; // ps points to a structure S }  
```  
  
 Vous recevez également cette erreur si vous utilisez une syntaxe incorrecte lors de l’utilisation des Extensions managées. Si vous pouvez utiliser l’opérateur point pour accéder au membre d’une classe managée dans d’autres langages de Visual Studio, un pointeur vers l’objet en C\+\+ signifie que vous devez utiliser l’opérateur \-\> pour accéder au membre :  
  
 Incorrect : `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Correct : `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`