---
title: "Avertissement du compilateur (niveau 3) C4538 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4538"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4538"
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur (niveau 3) C4538
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : les qualificateurs const\/volatile pour ce type ne sont pas pris en charge  
  
 Un mot clé de qualificateur n'a pas été appliqué correctement à un tableau.  Pour plus d'informations, consultez [array](../../windows/arrays-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C4538 :  
  
```  
// C4538.cpp  
// compile with: /clr /W3 /LD  
const array<int> ^f1();   // C4538  
array<const int> ^f2();   // OK  
```