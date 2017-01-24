---
title: "Erreur du compilateur C2498 | Microsoft Docs"
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
  - "C2498"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2498"
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2498
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : 'novtable' ne peut s'appliquer qu'aux définitions ou déclarations de classes  
  
 Cette erreur peut être provoquée par l'utiilsation de `__declspec(novtable)` avec une fonction.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2498 :  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```