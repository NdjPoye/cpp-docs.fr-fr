---
title: "Avertissement du compilateur (niveau 1) C4733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4733"
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

assignation de Inline asm à 'FS:0' : gestionnaire non inscrit en tant que gestionnaire safe  
  
 Une fonction modifiant la valeur en FS:0 pour ajouter un nouveau gestionnaire d'exceptions pourrait ne pas fonctionner avec les exceptions sécurisées car le gestionnaire pourrait ne pas être inscrit comme gestionnaire d'exceptions valide \(consultez [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)\).  
  
 Pour corriger cet avertissement, supprimez la définition FS:0 ou désactivez cet avertissement et utilisez [.SAFESEH](../../assembler/masm/dot-safeseh.md) pour spécifier les gestionnaires d'exceptions sécurisés.  
  
 L'exemple suivant génère l'erreur C4733 :  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```