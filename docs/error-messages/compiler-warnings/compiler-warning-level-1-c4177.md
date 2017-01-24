---
title: "Avertissement du compilateur (niveau&#160;1) C4177 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4177"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4177"
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4177
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'pragma' doit être uniquement utilisé au niveau de la portée globale  
  
 Le pragma [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) ne doit pas être utilisé dans une portée locale. Le **pragma** n’est pas valide si une portée globale est rencontrée après la portée actuelle.  
  
 L’exemple suivant génère l’avertissement C4177 :  
  
```  
// C4177.cpp // compile with: /W1 // #pragma bss_seg("global")   // OK int main() { #pragma bss_seg("local")    // C4177 }  
```