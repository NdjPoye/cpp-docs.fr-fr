---
title: "_heapadd | Microsoft Docs"
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
  - "_heapadd"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "heapadd"
  - "_heapadd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapadd (fonction)"
  - "heapadd (fonction)"
  - "tas, ajouter de la mémoire"
  - "mémoire, ajouter à des tas"
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapadd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute de la mémoire au tas.  
  
> [!IMPORTANT]
>  Cette fonction est obsolète. Depuis Visual Studio 2015, elle n’est pas disponible dans la bibliothèque CRT.  
  
## Syntaxe  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### Paramètres  
 `memblock`  
 Pointeur vers la mémoire du tas.  
  
 `size`  
 Taille de la mémoire à ajouter, en octets.  
  
## Valeur de retour  
 En cas de réussite, `_heapadd` retourne 0 ; sinon, la fonction retourne \-1 et définit `errno` sur `ENOSYS`.  
  
 Pour plus d’informations sur ce code de retour et sur les autres codes, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Depuis Visual C\+\+ version 4.0, la structure sous\-jacente du tas a été déplacée dans les bibliothèques Runtime C pour prendre en charge les nouvelles fonctionnalités de débogage. Par conséquent, `_heapadd` n’est plus pris en charge sur aucune des plateformes basées sur l’API Win32.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_heapadd`|\<malloc.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)