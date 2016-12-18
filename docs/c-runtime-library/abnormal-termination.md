---
title: "_abnormal_termination | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_abnormal_termination"
apilocation: 
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_abnormal_termination"
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _abnormal_termination
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si le bloc `__finally` d'une [instruction TRY\-finalement](../cpp/try-finally-statement.md) est écrit alors que le système effectue une liste interne de gestionnaires de terminaisons.  
  
## Syntaxe  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## Valeur de retour  
 `true` si le système *déroule* la pile ; sinon, `false`.  
  
## Notes  
 Il s'agit d'une fonction interne utilisée pour gérer les exceptions déroulantes, et n'est pas destinée à être appelée à partir d'un code utilisateur.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_abnormal\_termination|excpt.h|  
  
## Voir aussi  
 [try\-finally, instruction](../cpp/try-finally-statement.md)