---
title: "Avertissement du compilateur (niveau 1) C4083 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4083"
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'jeton' attendu ; identificateur 'identificateur' trouvé  
  
 Un identificateur apparaît à un emplacement erroné dans une instruction **\#pragma**.  
  
## Exemple  
  
```  
// C4083.cpp  
// compile with: /W1 /LD  
#pragma warning disable:4083    // C4083  
#pragma warning(disable:4083)   //correct  
```  
  
 Vérifiez la syntaxe des directives [\#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).