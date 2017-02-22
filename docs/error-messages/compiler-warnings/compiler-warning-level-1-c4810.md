---
title: "Avertissement du compilateur (niveau&#160;1) C4810 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4810"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4810"
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;1) C4810
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

valeur de pragma pack\(show\) \=\= n  
  
 Cet avertissement s’affiche quand vous utilisez l’option **Afficher** du pragma [pack](../../preprocessor/pack.md).*n* est la valeur actuelle du pragma pack.  
  
 Par exemple, le code suivant montre comment l’avertissement C4810 fonctionne avec le pragma pack :  
  
```  
// C4810.cpp // compile with: /W1 /LD // C4810 expected #pragma pack(show) #pragma pack(4) #pragma pack(show)  
```