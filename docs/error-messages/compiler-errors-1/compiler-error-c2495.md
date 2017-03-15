---
title: "Erreur du compilateur C2495 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2495"
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : '\_\_declspec\(nothrow\)' ne peut s'appliquer qu'aux définitions ou déclarations de fonctions  
  
 L'attribut étendu [nothrow](../../cpp/nothrow-cpp.md) ne peut s'appliquer qu'aux déclarations ou aux définitions de fonctions.  
  
 L'exemple suivant génère l'erreur C2495 :  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```