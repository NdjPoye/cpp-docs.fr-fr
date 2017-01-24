---
title: "_getcwd_dbg, _wgetcwd_dbg | Microsoft Docs"
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
  - "_wgetcwd_dbg"
  - "_getcwd_dbg"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd_dbg"
  - "_wgetcwd_dbg"
  - "getcwd_dbg"
  - "wgetcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getcwd_dbg (fonction)"
  - "_wgetcwd_dbg (fonction)"
  - "répertoire de travail en cours"
  - "répertoires (C++), de travail en cours"
  - "getcwd_dbg (fonction)"
  - "wgetcwd_dbg (fonction)"
  - "répertoire de travail"
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getcwd_dbg, _wgetcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versions de débogage des fonctions [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) \(disponibles uniquement durant le débogage\).  
  
## Syntaxe  
  
```  
char *_getcwd_dbg(     char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetcwd_dbg(     wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour le chemin d'accès.  
  
 `maxlen`  
 Longueur maximale du chemin d'accès en caractères : `char` pour `_getcwd_dbg` et `wchar_t` pour `_wgetcwd_dbg`.  
  
 `blockType`  
 Type demandé du bloc de mémoire : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## Valeur de retour  
 Retourne un pointeur vers `buffer`.  Une valeur de retour `NULL` indique une erreur et `errno` prend la valeur `ENOMEM`, ce qui indique que la mémoire est insuffisante pour allouer `maxlen` octets \(quand un argument `NULL` est donné comme `buffer`\), ou la valeur `ERANGE`, ce qui indique que le chemin d'accès fait plus de `maxlen` caractères.  
  
 Pour plus d'informations, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Les fonctions `_getcwd_dbg` et `_wgetcwd_dbg` sont identiques à `_getcwd` et `_wgetcwd` sauf que, quand \_`DEBUG` est défini, ces fonctions utilisent la version de débogage de `malloc` et `_malloc_dbg` pour allouer la mémoire si la valeur `NULL` est passée comme premier paramètre.  Pour plus d'informations, voir [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite.  À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`.  Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_getcwd`et `_wgetcwd`sont remappés à `_getcwd_dbg`et `_wgetcwd_dbg`, respectivement, avec le`blockType` défini sur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`.  Pour plus d'informations, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h\>|  
|`_wgetcwd_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A>  
  
## Voir aussi  
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)