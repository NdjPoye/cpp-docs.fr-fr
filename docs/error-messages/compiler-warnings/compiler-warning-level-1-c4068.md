---
title: "Avertissement du compilateur (niveau&#160;1)&#160;C4068 | Microsoft Docs"
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
  - "C4068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4068"
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1)&#160;C4068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragma inconnu  
  
 Le compilateur a ignoré un [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) non reconnu. Vérifiez que le **pragma** est autorisé par le compilateur que vous utilisez. L’exemple suivant génère l’avertissement C4068 :  
  
```  
// C4068.cpp // compile with: /W1 #pragma NotAValidPragmaName   // C4068, use valid name to resolve int main() { }  
```