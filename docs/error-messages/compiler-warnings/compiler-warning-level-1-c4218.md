---
title: "Avertissement du compilateur (niveau 1) C4218 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4218"
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : obligation de spécifier au moins une classe de stockage ou un type  
  
 Avec les extensions Microsoft par défaut \(\/Ze\), vous pouvez déclarer une variable sans spécifier un type ni une classe de stockage.  Le type par défaut est `int`.  
  
## Exemple  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 Ces déclarations sont non valides sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).