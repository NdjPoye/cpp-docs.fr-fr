---
title: "Erreur du compilateur C2693 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2693"
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Erreur du compilateur C2693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : comparaison non conforme entre des références et un tableau managé ou WinRT  
  
 Vous ne pouvez pas tester un tableau managé ou WinRT pour un type quelconque d'inégalité.  Par exemple, vous pouvez tester pour voir si des tableaux managés sont égaux, mais vous ne pouvez pas vérifier si un tableau est supérieur ou inférieur à un autre tableau.  
  
 **Extensions managées pour C\+\+**  
  
 Vous ne pouvez pas tester un tableau [\_\_gc](../../misc/gc.md) pour un type quelconque d'inégalité.  Par exemple, vous pouvez tester pour voir si des tableaux managés sont égaux, mais vous ne pouvez pas vérifier si un tableau est supérieur ou inférieur à un autre tableau.  
  
 L'exemple suivant génère l'erreur C2693 :  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```