---
title: "__setusermatherr | Microsoft Docs"
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
  - "__setusermatherr"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__setusermatherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__setusermatherr"
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __setusermatherr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie un rountine fourni par l'utilisateur pour gérer les erreurs mathématiques, au lieu de la routine [\_matherr](../c-runtime-library/reference/matherr.md).  
  
## Syntaxe  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
  
```  
  
#### Paramètres  
 `pf`  
 Pointeur vers une implémentation de`_matherr`qui est fournie par l'utilisateur.  
  
 Le type du paramètre `pf` est déclaré comme `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`.  
  
## Notes  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_setusermatherr|matherr.c|