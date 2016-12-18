---
title: "_heapmin | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapmin"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_heapmin"
  - "heapmin"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapmin (fonction)"
  - "mémoire de tas"
  - "heapmin (fonction)"
  - "tas, libérer la mémoire non utilisée"
  - "mémoire, libération"
  - "réduire les tas"
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapmin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère la mémoire de segment de mémoire inutilisée du système d'exploitation.  
  
## Syntaxe  
  
```  
int _heapmin( void );  
```  
  
## Valeur de retour  
 En cas de réussite, retourne 0 pour `_heapmin` ; sinon, la fonction retourne – 1 et affecte `errno` à `ENOSYS`.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_heapmin` réduit le segment en libérant la mémoire de segment inutilisée du système d'exploitation.  Si le système d'exploitation ne prend pas en charge `_heapmin`\(par exemple, Windows 98\), la fonction retourne `errno` et affecte à la valeur`ENOSYS`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_heapmin`|\<malloc.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../../c-runtime-library/reference/heapwalk.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)