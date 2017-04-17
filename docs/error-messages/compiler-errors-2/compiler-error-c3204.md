---
title: "Erreur du compilateur C3204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3204"
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_alloca' ne peut pas être appelé à partir d’un bloc catch  
  
 Cette erreur se produit quand vous utilisez un appel à [\_alloca](../../c-runtime-library/reference/alloca.md) à partir d’un bloc catch.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3204 :  
  
```  
// C3204.cpp // compile with: /EHsc #include <malloc.h> void ShowError(void) { try { } catch(...) { _alloca(1);   // C3204 } }  
```