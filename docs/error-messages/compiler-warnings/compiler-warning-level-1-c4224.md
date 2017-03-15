---
title: "Avertissement du compilateur (niveau 1) C4224 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4224"
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : paramètre formel 'identificateur' préalablement défini comme type  
  
 L'identificateur a été utilisé précédemment avec un `typedef`.  Ceci génère un avertissement sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
## Exemple  
  
```  
// C4224.cpp  
// compile with: /Za /W1 /LD  
typedef int I;  
void func ( int I );  // C4224  
```