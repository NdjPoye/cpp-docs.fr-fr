---
title: "Avertissement du compilateur (niveau&#160;1) C4186 | Microsoft Docs"
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
  - "C4186"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4186"
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4186
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L’attribut \#import 'attribut' nécessite 'nombre' arguments ; il sera ignoré  
  
 Un attribut `#import` présente un nombre incorrect d’arguments.  
  
## Exemple  
  
```  
// C4186.cpp // compile with: /W1 /c #import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 L’attribut `no_namespace` n’accepte aucun argument. L’attribut **rename** accepte uniquement deux arguments.