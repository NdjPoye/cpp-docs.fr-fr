---
title: "Avertissement du compilateur (niveau 1) C4399 | Microsoft Docs"
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
  - "C4399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4399"
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : un symbole par processus ne doit pas être marqué avec \_\_declspec\(dllimport\) lorsqu'il est compilé avec \/clr:pure  
  
 Les données d'une image native ou d'une image avec des constructions natives et CLR ne peuvent pas être importées dans une image pure.  Pour remédier à cet avertissement, compilez avec **\/clr** \(pas **\/clr:pure**\) ou supprimez `__declspec(dllimport)`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4399 :  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```