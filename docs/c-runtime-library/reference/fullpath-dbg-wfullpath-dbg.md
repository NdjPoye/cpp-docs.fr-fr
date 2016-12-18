---
title: "_fullpath_dbg, _wfullpath_dbg | Microsoft Docs"
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
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
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
  - "wfullpath_dbg"
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
  - "fullpath_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fullpath_dbg (fonction)"
  - "_wfullpath_dbg (fonction)"
  - "chemins d'accès absolus"
  - "fullpath_dbg (fonction)"
  - "chemins d'accès de fichier relatifs"
  - "wfullpath_dbg (fonction)"
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fullpath_dbg, _wfullpath_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versions de [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md) qui utilisent la version de débogage de `malloc` pour allouer de la mémoire.  
  
## Syntaxe  
  
```  
char *_fullpath_dbg(     char *absPath,    const char *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wfullpath_dbg(     wchar_t *absPath,    const wchar_t *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `absPath`  
 Pointeur vers une mémoire tampon contenant le nom de chemin d'accès absolu ou complet, ou `NULL`.  
  
 `relPath`  
 Nom de chemin d'accès relatif.  
  
 `maxLength`  
 Longueur maximale de la mémoire tampon du nom de chemin d'accès absolu \(`absPath`\).  Cette longueur est représentée en octets pour `_fullpath` mais en caractères larges \(`wchar_t`\) pour `_wfullpath`.  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## Valeur de retour  
 Chaque fonction retourne un pointeur vers une mémoire tampon contenant le nom de chemin d'accès absolu \(`absPath`\).  En cas d'erreur \(par exemple, si la valeur passée dans `relPath` comprend une lettre de lecteur qui n'est pas valide ou qui est introuvable, ou si la longueur du nom de chemin d'accès absolu créé \(`absPath`\) est supérieure à `maxLength`\) la fonction retourne `NULL`.  
  
## Notes  
 Les fonctions `_fullpath_dbg` et `_wfullpath_dbg` sont identiques à `_fullpath` et `_wfullpath` sauf que, quand **\_**`DEBUG` est défini, ces fonctions utilisent la version de débogage de `malloc`, `_malloc_dbg` pour allouer la mémoire si la valeur Null est passée comme premier paramètre.  Pour plus d'informations sur les fonctionnalités de débogage de `_malloc_dbg`, voir [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite.  À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`.  Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_fullpath` et `_wfullpath`sont remappés à `_fullpath_dbg` et `_wfullpath_dbg`, respectivement, avec le`blockType` défini sur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`.  Pour plus d'informations, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fullpath_dbg`|\<crtdbg.h\>|  
|`_wfullpath_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 <xref:System.IO.File.Create%2A>  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)