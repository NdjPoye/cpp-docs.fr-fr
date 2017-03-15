---
title: "Avertissement du compilateur (niveau 1) C4215 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4215"
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : flottant long  
  
 Les extensions Microsoft par défaut \(\/Ze\) traitent les **long float** comme des **double**.  La compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ne le fait pas.  Utilisez **double** pour assurer la compatibilité.  
  
 L'exemple suivant génère l'erreur C4215 :  
  
```  
// C4215.cpp  
// compile with: /W1 /LD  
long float a;   // C4215  
  
// use the line below to resolve the warning  
// double a;  
```