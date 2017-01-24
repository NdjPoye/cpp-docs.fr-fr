---
title: "_unlock | Microsoft Docs"
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
  - "_unlock"
apilocation: 
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr120_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "unlock"
  - "_unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unlock (fonction)"
  - "_unlock (fonction)"
ms.assetid: 2eda2507-a134-4997-aa12-f2f8cb319e14
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _unlock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère un verrou multithread.  
  
> [!IMPORTANT]
>  Cette fonction est obsolète. Depuis Visual Studio 2015, elle n’est pas disponible dans la bibliothèque CRT.  
  
## Syntaxe  
  
```  
void __cdecl _unlock(  
   int locknum  
);  
```  
  
#### Paramètres  
 \[in\] `locknum`  
 L’identificateur du verrou à libérer.  
  
## Configuration requise  
 **Source :** mlock.c  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_lock](../c-runtime-library/lock.md)