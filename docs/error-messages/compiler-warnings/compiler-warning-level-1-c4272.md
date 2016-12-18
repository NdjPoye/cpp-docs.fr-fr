---
title: "Avertissement du compilateur (niveau 1) C4272 | Microsoft Docs"
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
  - "C4272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4272"
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : est marqué comme \_\_declspec\(dllimport\) ; une convention d'appel native doit être spécifiée lors de l'importation d'une fonction.  
  
 Il s'agit d'une erreur d'exportation d'une fonction marquée avec la convention d'appel [\_\_clrcall](../../cpp/clrcall.md) ; le compilateur émet cet avertissement si vous essayez d'importer une fonction marquée `__clrcall`.  
  
 L'exemple suivant génère l'erreur C4272 :  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```