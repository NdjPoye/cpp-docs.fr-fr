---
title: "Avertissement du compilateur (niveau&#160;3) C4645 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;3) C4645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la fonction déclarée avec \_\_declspec\(noreturn\) a une instruction return  
  
 Une instruction [return](../../cpp/return-statement-in-program-termination-cpp.md) instruction a été trouvée dans une fonction qui est marquée avec le modificateur [noreturn](../../cpp/noreturn.md) `__declspec`. L’instruction `return` a été ignorée.  
  
 L’exemple suivant génère l’avertissement C4645 :  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```