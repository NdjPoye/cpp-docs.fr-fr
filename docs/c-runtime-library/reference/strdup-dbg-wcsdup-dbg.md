---
title: "_strdup_dbg, _wcsdup_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup_dbg"
  - "_wcsdup_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_wcsdup_dbg"
  - "strdup_dbg"
  - "_strdup_dbg"
  - "wcsdup_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strdup_dbg (fonction)"
  - "_wcsdup_dbg (fonction)"
  - "copier des chaînes"
  - "dupliquer des chaînes"
  - "strdup_dbg (fonction)"
  - "chaînes (C++), copier"
  - "chaînes (C++), dupliquer"
  - "wcsdup_dbg (fonction)"
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _strdup_dbg, _wcsdup_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versions de [\_strdup et \_wcsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md) qui utilisent la version de débogage de `malloc`.  
  
## Syntaxe  
  
```  
char *_strdup_dbg(    const char *strSource,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wcsdup_dbg(    const wchar_t *strSource,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `strSource`  
 Chaîne source se terminant par null.  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou NULL.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou NULL.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers l'emplacement de stockage de la chaîne copiée ou `NULL` si le stockage ne peut pas être alloué.  
  
## Notes  
 Les fonctions `_strdup_dbg` et `_wcsdup_dbg` sont identiques à `_strdup` et `_wcsdup` sauf que, quand `_DEBUG` est défini, ces fonctions utilisent la version de débogage de `malloc`, `_malloc_dbg` pour allouer de la mémoire pour la chaîne dupliquée.  Pour plus d'informations sur les fonctionnalités de débogage de `_malloc_dbg`, voir [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite.  À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`.  Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_strdup` et `_wcsdup` sont remappés à `_strdup_dbg` et `_wcsdup_dbg`, respectivement, avec `blockType` défini sur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`.  Pour plus d'informations sur les types de blocs, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsdup_dbg`|`_strdup_dbg`|`_mbsdup`|`_wcsdup_dbg`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strdup_dbg`, `_wcsdup_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdup, \_wcsdup, \_mbsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)   
 [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)