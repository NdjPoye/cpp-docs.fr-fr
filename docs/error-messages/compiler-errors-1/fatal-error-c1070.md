---
title: "Erreur irr&#233;cup&#233;rable C1070 | Microsoft Docs"
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
  - "C1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1070"
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

non concordance \#if\/\#endif dans le fichier 'nom\_fichier'  
  
 Une directive `#if`, `#ifdef` ou `#ifndef` n’a pas de `#endif` correspondant.  
  
 L’exemple suivant génère l’erreur C1070 :  
  
```  
// C1070.cpp #define TEST #ifdef TEST #ifdef TEST #endif // C1070  
```  
  
 Solution possible :  
  
```  
// C1070b.cpp // compile with: /c #define TEST #ifdef TEST #endif #ifdef TEST #endif  
```