---
title: "Erreur irr&#233;cup&#233;rable C1019 | Microsoft Docs"
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
  - "C1019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1019"
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#else inattendu  
  
 La directive `#else` se trouve à l’extérieur d’une construction `#if`, `#ifdef` ou `#ifndef`. Utilisez `#else` uniquement dans l’une de ces constructions.  
  
 L’exemple suivant génère l’erreur C1019 :  
  
```  
// C1019.cpp #else   // C1019 #endif int main() {}  
```  
  
 Résolution possible :  
  
```  
// C1019b.cpp #if 1 #else #endif int main() {}  
```