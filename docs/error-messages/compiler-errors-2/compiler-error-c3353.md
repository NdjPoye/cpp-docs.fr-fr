---
title: "Compiler Error C3353 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3353"
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Error C3353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'délégué' : un délégué ne peut être créé qu'à partir d'une fonction globale ou à partir d'une fonction membre d'un type managé ou WinRT  
  
 Les délégués, déclarés avec le mot clé [\_\_delegate](../../misc/delegate.md) ou [délégué](../../windows/delegate-cpp-component-extensions.md), peuvent uniquement être déclarés dans une portée globale.  
  
 L'exemple suivant génère l'erreur C3353 :  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```