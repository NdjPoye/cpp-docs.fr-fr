---
title: "Erreur du compilateur C3389 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3389"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3389"
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3389
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(keyword\) ne peut pas être utilisé avec \/clr:pure ou \/clr:safe  
  
 Un modificateur [\_\_declspec](../../cpp/declspec.md) utilisé implique un état par processus.  [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) implique un état par [appdomain](../../cpp/appdomain.md).  Ainsi, la déclaration d'une variable avec le modificateur `keyword` **\_\_declspec** et la compilation avec **\/clr:pure** ne sont pas autorisées.  
  
 L'exemple suivant génère l'erreur C3389 :  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```