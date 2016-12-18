---
title: "Erreur du compilateur C2033 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2033"
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : un champ de bits ne peut pas avoir d’indirection  
  
 Le champ de bits a été déclaré en tant que pointeur, ce qui n’est pas autorisé.  
  
 L’exemple suivant génère l’erreur C2033 :  
  
```  
// C2033.cpp struct S { int *b : 1;  // C2033 };  
```  
  
 Résolution possible :  
  
```  
// C2033b.cpp // compile with: /c struct S { int b : 1; };  
```