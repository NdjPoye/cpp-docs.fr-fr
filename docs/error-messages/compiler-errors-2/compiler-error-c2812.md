---
title: "Erreur du compilateur C2812 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2812"
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import n'est pas pris en charge avec \/clr:pure et \/clr:safe  
  
 [\#import, directive](../../preprocessor/hash-import-directive-cpp.md) n'est pas prise en charge avec **\/clr:pure** et **\/clr:safe** car `#import` requiert l'utilisation de bibliothèques de prise en charge du compilateur natif.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2812 :  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```