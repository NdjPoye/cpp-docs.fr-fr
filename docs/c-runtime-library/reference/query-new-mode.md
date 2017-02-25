---
title: "_query_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_mode"
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
  - "query_new_mode"
  - "_query_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_mode (fonction)"
  - "modes de gestionnaire"
  - "query_new_mode (fonction)"
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un entier, qui indique le nouveau mode du gestionnaire défini par `_set_new_mode`pour `malloc`  
  
## Syntaxe  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## Valeur de retour  
 Retourne le nouveau mode gestionnaire actuel, à savoir 0 ou 1, pour `malloc`.  Une valeur de retour de 1 indique que, en cas de échec d'allocation de mémoire, `malloc` appelle la nouvelle routine du gestionnaire ; une valeur de retour de 0 indique que ce n'est pas le cas.  
  
## Notes  
 La fonction C\+\+ `_query_new_mode` retourne un entier qui indique le nouveau mode gestionnaire, qui est défini par la fonction C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) pour [malloc](../../c-runtime-library/reference/malloc.md).  Le nouveau mode gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine de gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas d'échec.  Vous pouvez utiliser `_set_new_mode` pour prendre le pas sur ce comportement pour qu'en cas d'échec `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur **new** lorsqu'il échoue à allouer de la mémoire.  Pour plus d'informations, consultez [suppression d'opérateur](../../misc/operator-delete-function.md) et les fonctions [opérateur nouveau](../../misc/operator-new-function.md) dans  *Guide de référence du langage C\+\+*.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)