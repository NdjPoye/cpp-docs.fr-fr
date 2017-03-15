---
title: "Erreur du compilateur C2165 | Microsoft Docs"
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
  - "C2165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2165"
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' : impossible de modifier les pointeurs vers des données  
  
 Le mot clé `__stdcall`, `__cdecl` ou `__fastcall` tente de modifier un pointeur vers des données.  
  
 L’exemple suivant génère l’erreur C2165 :  
  
```  
// C2165.cpp // compile with: /c char __cdecl *p;   // C2165 char *p;   // OK  
```