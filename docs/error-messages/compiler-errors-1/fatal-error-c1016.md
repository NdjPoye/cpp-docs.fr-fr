---
title: "Erreur irr&#233;cup&#233;rable C1016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1016"
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur irr&#233;cup&#233;rable C1016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#ifdef attendait un identificateur \#ifndef attendait un identificateur  
  
 La directive de compilation conditionnelle \([\#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) ou `#ifndef`\) n’a aucun identificateur à évaluer. Pour résoudre l’erreur, spécifiez un identificateur.  
  
 L’exemple suivant génère l’erreur C1016 :  
  
```  
// C1016.cpp #ifdef   // C1016 #define FC1016 #endif int main() {}  
```  
  
 Résolution possible :  
  
```  
// C1016b.cpp #ifdef X #define FC1016 #endif int main() {}  
```