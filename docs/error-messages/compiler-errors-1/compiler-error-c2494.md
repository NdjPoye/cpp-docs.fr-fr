---
title: "Erreur du compilateur C2494 | Microsoft Docs"
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
  - "C2494"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2494"
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2494
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'MotClé' ne peut pas être appelé à partir d'une expression de filtre ou d'un bloc \_\_finally\/finally  
  
 Vous ne pouvez pas utiliser `keyword` dans un bloc `__finally`.  
  
 L'exemple suivant génère l'erreur C2494 :  
  
```  
// C2494.cpp  
#include <malloc.h>  
  
int main() {  
   __try {}  
   __except ( _alloca(100), 1 ) {}   // C2494  
   __try {}  
   __finally {  
      _alloca(100);   // C2494  
   }  
}  
```  
  
 L'erreur C2494 peut également se produire lors de l'utilisation de **\/clr**.  
  
```  
// C2494b.cpp  
// compile with: /clr  
#include <malloc.h>  
  
int main() {  
   char * buf;  
   try {}  
   catch (char * buf2) {}  
   finally {  
      _alloca(100);   // C2494  
   }  
}  
```