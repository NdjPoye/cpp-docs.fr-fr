---
title: "Avertissement du compilateur (niveau&#160;4) C4131 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4131"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4131"
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;4) C4131
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : utilise un déclarateur obsolète  
  
 La déclaration de fonction spécifiée n’est pas sous forme de prototype.  
  
 Les anciennes déclarations de fonction doivent être converties sous forme de prototypes.  
  
 L’exemple suivant montre une ancienne déclaration de fonction :  
  
```  
// C4131.c // compile with: /W4 /c void addrec( name, id ) // C4131 expected char *name; int id; { }  
```  
  
 L’exemple suivant montre une forme de prototype :  
  
```  
void addrec( char *name, int id ) { }  
```