---
title: "MMWORD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MMWORD directive"
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# MMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé pour les opérandes multimédias 64 bits avec l'instruction de MMX et de SSE \(XMM\).  
  
## Syntaxe  
  
```  
MMWORD  
```  
  
## Notes  
 `MMWORD` est un type.  Avant MMWORD ajouté à MASM, la fonctionnalité équivalente peut avoir été effectuée avec :  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Bien que les deux instructions fonctionne sur les opérandes 64 bits, `QWORD` est le type pour les entiers non signés 64 bits et `MMWORD` est le type pour une valeur 64 bits de média.  
  
 `MMWORD` est conçu pour représenter le même type que [\_\_m64](../../cpp/m64.md).  
  
## Exemple  
  
```  
movq     mm0, mmword ptr [ebx]  
```