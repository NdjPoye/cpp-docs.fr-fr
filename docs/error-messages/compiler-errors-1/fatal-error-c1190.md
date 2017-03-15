---
title: "Erreur irr&#233;cup&#233;rable C1190 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1190"
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Erreur irr&#233;cup&#233;rable C1190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le code ciblé managé requiert une option '\/clr'  
  
 Vous utilisez des constructions CLR, mais vous n’avez pas spécifié **\/clr**.  
  
 Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L’exemple suivant génère l’erreur C1190 :  
  
```  
// C1190.cpp // compile with: /c __gc class A {};   // C1190 ref class A {};  
```