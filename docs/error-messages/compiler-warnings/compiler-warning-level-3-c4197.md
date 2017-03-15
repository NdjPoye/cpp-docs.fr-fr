---
title: "Avertissement du compilateur (niveau 3) C4197 | Microsoft Docs"
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
  - "C4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4197"
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : le qualificateur 'volatile' de niveau supérieur dans le cast est ignoré  
  
 Le compilateur a détecté un cast de type vers un type r\-value qualifié [volatile](../../cpp/volatile-cpp.md) ou un cast de type d'un type r\-value vers un autre type qualifié de volatile.  Conformément à la norme C \(6.5.3\), les propriétés associées aux types qualifiés n'ont de sens que pour les expressions l\-value.  
  
 L'exemple suivant génère l'erreur C4197 :  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```