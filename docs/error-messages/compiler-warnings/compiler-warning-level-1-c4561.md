---
title: "Avertissement du compilateur (niveau 1) C4561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4561"
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 1) C4561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_fastcall' incompatible avec l'option '\/clr' : conversion en '\_\_stdcall'  
  
 La convention d'appel de fonction [\_\_fastcall](../../cpp/fastcall.md) ne peut pas être utilisée avec l'option du compilateur [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  Le compilateur ignore les appels à `__fastcall`.  Pour remédier à cet avertissement, vous pouvez supprimer les appels **\_\_fastcall** ou compiler sans **\/clr**.  
  
 L'exemple suivant génère l'erreur C4561 :  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```