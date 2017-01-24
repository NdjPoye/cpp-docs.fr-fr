---
title: "Erreur du compilateur C3470 | Microsoft Docs"
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
  - "C3470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3470"
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe ne peut pas avoir à la fois un indexeur \(propriété indexée par défaut\) et operator\[\]  
  
 Un type ne peut pas définir à la fois un indexeur par défaut et un operator\[\].  
  
## Exemple  
 L’exemple suivant génère l’erreur C3470.  
  
```  
// C3470.cpp // compile with: /clr using namespace System; ref class R { public: property int default[int] { int get(int i) { return i+1; } } int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470 }; int main() { R ^ r = gcnew R; // return r[9] + r["32"] - 42; }  
```