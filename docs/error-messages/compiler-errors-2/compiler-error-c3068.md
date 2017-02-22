---
title: "Erreur du compilateur C3068 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3068"
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : une fonction 'naked' ne peut pas contenir d'objets qui requièrent un déroulement si une exception C\+\+ se produit  
  
 Le compilateur n'a pas pu exécuter le déroulement de pile sur une fonction [naked](../../cpp/naked-cpp.md) qui a levé une exception, car un objet temporaire a été créé dans la fonction et la gestion des exceptions C\+\+ \([\/EHsc](../../build/reference/eh-exception-handling-model.md)\) a été spécifiée.  
  
 Pour remédier à cette erreur, effectuez au moins l'une des opérations suivantes :  
  
-   Ne compilez pas avec \/EHsc.  
  
-   Ne marquez pas la fonction comme `naked`.  
  
-   Ne créez pas d'objet temporaire dans la fonction.  
  
 Si une fonction crée un objet temporaire sur la pile, si la fonction lève une exception et si la gestion des exceptions C\+\+ est activée, le compilateur nettoie la pile en cas de levée d'une exception.  
  
 Lorsqu'une exception est levée, le code généré par le compilateur, appelé prologue et épilogue, qui n'est pas présent dans une fonction naked, est exécuté pour une fonction.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3068 :  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```