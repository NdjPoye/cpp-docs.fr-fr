---
title: "Erreur du compilateur C2710 | Microsoft Docs"
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
  - "C2710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2710"
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construct' : '\_\_declspec\(modifier\)' ne peut s'appliquer qu'à une fonction qui retourne un pointeur  
  
 Une fonction dont la valeur de retour est un pointeur est la seule construction à laquelle `modifier` peut être appliqué.  
  
 L'exemple suivant génère l'erreur C2710 :  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```