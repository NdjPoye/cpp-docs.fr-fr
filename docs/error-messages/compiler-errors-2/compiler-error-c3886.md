---
title: "Erreur du compilateur C3886 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3886"
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : une donnée membre littérale doit être initialisée  
  
 Une variable [littérale](../../windows/literal-cpp-component-extensions.md) doit être initialisée lorsqu'elle est déclarée.  
  
 L'exemple suivant génère l'erreur C3886 :  
  
```  
// C3886.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal int staticConst;   // C3886  
   literal int staticConst2 = 0;   // OK  
};  
```