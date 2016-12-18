---
title: "_tempnam_dbg, _wtempnam_dbg | Microsoft Docs"
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
  - "_wtempnam_dbg"
  - "_tempnam_dbg"
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
  - "wtempnam_dbg"
  - "tempnam_dbg"
  - "_tempnam_dbg"
  - "_wtempnam_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tempnam_dbg (fonction)"
  - "_wtempnam_dbg (fonction)"
  - "noms de fichiers (C++), créer temporaire"
  - "noms de fichiers (C++), temporaires"
  - "tempnam_dbg (fonction)"
  - "fichiers temporaires, créer"
  - "wtempnam_dbg (fonction)"
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _tempnam_dbg, _wtempnam_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versions des fonctions [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) qui utilisent la version de débogage de `malloc, _malloc_dbg`.  
  
## Syntaxe  
  
```  
char *_tempnam_dbg(    const char *dir,    const char *prefix,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wtempnam_dbg(    const wchar_t *dir,    const wchar_t *prefix,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `dir`  
 Chemin d'accès utilisé dans le nom de fichier en l'absence de variable d'environnement TMP ou si TMP n'est pas un répertoire valide.  
  
 `prefix`  
 Chaîne qui sera ajoutée aux noms retournés par `_tempnam`.  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK`ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## Valeur de retour  
 Chaque fonction retourne un pointeur vers le nom généré ou `NULL` en cas de défaillance.  Une défaillance peut se produire si un nom de répertoire non valide a été spécifié dans la variable d'environnement TMP et dans le paramètre `dir`.  
  
> [!NOTE]
>  `free` \(ou `free_dbg`\) doit être appelé pour les pointeurs alloués par `_tempnam_dbg` et `_wtempnam_dbg`.  
  
## Notes  
 Les fonctions `_tempnam_dbg`et `_wtempnam_dbg`sont identiques à `_tempnam`et `_wtempnam`sauf que, quand `_DEBUG`est défini, ces fonctions utilisent la version de débogage de `malloc` et `_malloc_dbg` pour allouer la mémoire si la valeur `NULL` est passée comme premier paramètre.  Pour plus d'informations, voir [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite.  À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`.  Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_tempnam` et `_wtempnam` sont remappés à  `_tempnam_dbg` et `_wtempnam_dbg`, respectivement, avec le `blockType` défini sur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`.  Pour plus d'informations, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)