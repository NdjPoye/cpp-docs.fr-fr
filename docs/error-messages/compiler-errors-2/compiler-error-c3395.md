---
title: "Erreur du compilateur C3395 | Microsoft Docs"
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
  - "C3395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3395"
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : \_\_declspec\(dllexport\) ne peut pas être appliqué à une fonction avec la convention d'appel \_\_clrcall  
  
 `__declspec(dllexport)` et [\_\_clrcall](../../cpp/clrcall.md) ne sont pas compatibles.  Pour plus d'informations, consultez [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
 L'exemple suivant génère l'erreur C3395 :  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```