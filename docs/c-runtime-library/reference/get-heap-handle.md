---
title: "_get_heap_handle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_heap_handle"
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
  - "_get_heap_handle"
  - "get_heap_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions du tas"
  - "allocation de mémoire, mémoire de tas"
  - "_get_heap_handle (fonction)"
  - "get_heap_handle (fonction)"
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _get_heap_handle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne le handle du tas utilisé par le système runtime C.  
  
## Syntaxe  
  
```  
intptr_t _get_heap_handle( void );  
```  
  
## Valeur de retour  
 Retourne le handle vers le tas Win32 utilisé par le système runtime C.  
  
## Notes  
 Utilisez cette fonction pour appeler [HeapSetInformation](http://msdn.microsoft.com/library/windows/desktop/aa366705) et activer le tas LFH \(Low Fragmentation Heap\) sur le tas CRT.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_heap_handle`|\<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_get_heap_handle.cpp  
// compile with: /MT  
#include <windows.h>  
#include <malloc.h>  
#include <stdio.h>  
  
int main(void)  
{  
    intptr_t hCrtHeap = _get_heap_handle();  
    ULONG ulEnableLFH = 2;  
    if (HeapSetInformation((PVOID)hCrtHeap,  
                           HeapCompatibilityInformation,  
                           &ulEnableLFH, sizeof(ulEnableLFH)))  
        puts("Enabling Low Fragmentation Heap succeeded");  
    else  
        puts("Enabling Low Fragmentation Heap failed");  
    return 0;  
}  
```  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)