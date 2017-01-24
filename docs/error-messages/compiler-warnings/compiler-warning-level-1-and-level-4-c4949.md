---
title: "Avertissement du compilateur (niveaux&#160;1 et 4) C4949 | Microsoft Docs"
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
  - "C4949"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4949"
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveaux&#160;1 et 4) C4949
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les pragmas 'managed' et 'unmanaged' sont significatifs uniquement lorsqu'ils sont compilés avec '\/clr\[:option\]'  
  
 Le compilateur ignore les pragmas [managés](../../preprocessor/managed-unmanaged.md) et non managés si le code source n'est pas compilé avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  Cet avertissement est informatif.  
  
 L'exemple suivant génère l'erreur C4949 :  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 Lorsque **\#pragma unmanaged** est utilisé sans **\/clr**, l'erreur C4949 est un avertissement de niveau 4.  
  
 L'exemple suivant génère l'erreur C4949 :  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```