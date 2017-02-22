---
title: "_getdcwd_dbg, _wgetdcwd_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getdcwd_dbg"
  - "_wgetdcwd_dbg"
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
  - "_getdcwd_dbg"
  - "getdcwd_dbg"
  - "_wgetdcwd_dbg"
  - "wgetdcwd_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getdcwd_dbg (fonction)"
  - "_wgetdcwd_dbg (fonction)"
  - "répertoire de travail en cours"
  - "répertoires (C++), de travail en cours"
  - "getdcwd_dbg (fonction)"
  - "wgetdcwd_dbg (fonction)"
  - "répertoire de travail"
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _getdcwd_dbg, _wgetdcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versions de débogage des fonctions [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) \(disponibles uniquement durant le débogage\).  
  
## Syntaxe  
  
```  
char *_getdcwd_dbg(    int drive,    char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetdcwd_dbg(    int drive,    wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `drive`  
 Nom du lecteur de disque.  
  
 `buffer`  
 Emplacement de stockage pour le chemin d'accès.  
  
 `maxlen`  
 Longueur maximale du chemin d'accès en caractères : `char` pour `_getdcwd_dbg`et `wchar_t`pour `_wgetdcwd_dbg`.  
  
 `blockType`  
 Type demandé du bloc de mémoire : `_CLIENT_BLOCK`ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## Valeur de retour  
 Retourne un pointeur vers `buffer`.  Une valeur de retour `NULL` indique une erreur et `errno` prend la valeur `ENOMEM`, ce qui indique que la mémoire est insuffisante pour allouer `maxlen` octets \(quand un argument `NULL` est donné comme `buffer`\), ou la valeur `ERANGE`, ce qui indique que le chemin d'accès fait plus de `maxlen` caractères.  Pour plus d'informations, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Les fonctions `_getdcwd_dbg` et `_wgetdcwd_dbg` sont identiques à `_getdcwd` et `_wgetdcwd`, sauf quand `_DEBUG` est défini : ces fonctions utilisent alors la version de débogage de `malloc` et `_malloc_dbg` pour allouer de la mémoire si `NULL` est passé comme paramètre `buffer`.  Pour plus d'informations, voir [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite.  À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`.  Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_getdcwd` et `_wgetdcwd` sont remappés à `_getdcwd_dbg` et `_wgetdcwd_dbg`, respectivement, avec `blockType` défini sur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`.  Pour plus d'informations, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getdcwd_dbg`|\<crtdbg.h\>|  
|`_wgetdcwd_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A?displayProperty=fullName>  
  
## Voir aussi  
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)