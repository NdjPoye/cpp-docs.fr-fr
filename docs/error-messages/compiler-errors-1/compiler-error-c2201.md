---
title: "Erreur du compilateur C2201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2201"
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : doit avoir une liaison externe pour pouvoir être importé\/exporté  
  
 L'identificateur exporté est `static`.  
  
 L'exemple suivant génère l'erreur C2286 :  
  
```  
// C2201.cpp  
// compile with: /c  
__declspec(dllexport) static void func() {}   // C2201 func() is static  
__declspec(dllexport) void func2() {}   // OK  
```  
  
## Voir aussi  
 [Types de liaison](../../cpp/types-of-linkage.md)