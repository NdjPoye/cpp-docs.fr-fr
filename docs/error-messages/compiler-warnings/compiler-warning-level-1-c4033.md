---
title: "Avertissement du compilateur (niveau&#160;1) C4033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4033"
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' doit retourner une valeur  
  
 La fonction ne retourne pas de valeur. Une valeur non définie est retournée.  
  
 Les fonctions qui utilisent `return` sans valeur de retour doivent être déclarées comme type `void`.  
  
 Cette erreur concerne le code de langage C.  
  
 L’exemple suivant génère l’avertissement C4033 :  
  
```  
// C4033.c // compile with: /W1 /LD int test_1(int x)   // C4033 expected { if (x) { return;   // C4033 } }  
```