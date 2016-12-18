---
title: "Avertissement du compilateur (niveau&#160;1) C4080 | Microsoft Docs"
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
  - "C4080"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4080"
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4080
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identificateur attendu pour le nom du segment ; 'symbol' trouvé  
  
 Le nom du segment dans [\#pragma alloc\_text](../../preprocessor/alloc-text.md) doit être une chaîne ou un identificateur. Le compilateur ignore le pragma si un identificateur valide est introuvable.  
  
 L’exemple suivant génère l’avertissement C4080 :  
  
```  
// C4080.cpp // compile with: /W1 extern "C" void func(void); #pragma alloc_text()   // C4080 // try this line to resolve the warning // #pragma alloc_text("mysection", func) int main() { } void func(void) { }  
```