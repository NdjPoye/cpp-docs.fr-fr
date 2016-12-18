---
title: "_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfindnext"
  - "_findnext"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "findnext"
  - "_wfindnext32i64"
  - "_tfindnext64i32"
  - "findnext32"
  - "findnext32i64"
  - "wfindnext64i32"
  - "_wfindnext"
  - "tfindnext64"
  - "findnexti64"
  - "_findnexti64"
  - "_tfindnexti64"
  - "_findnext64i32"
  - "tfindnexti64"
  - "tfindnext32"
  - "_wfindnext64i32"
  - "findnext64i32"
  - "_findnext"
  - "_tfindnext32i64"
  - "_wfindnext64"
  - "wfindnext"
  - "wfindnext32"
  - "tfindnext32i64"
  - "_findnext64"
  - "_tfindnext64"
  - "_wfindnext32"
  - "findnext64"
  - "_findnext32i64"
  - "tfindnext"
  - "wfindnexti64"
  - "tfindnext64i32"
  - "_tfindnext32"
  - "wfindnext32i64"
  - "wfindnext64"
  - "_wfindnexti64"
  - "_tfindnext"
  - "_findnext32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wfindnexti64 (fonction)"
  - "_tfindnext32 (fonction)"
  - "wfindnexti64 (fonction)"
  - "_wfindnext32i64 (fonction)"
  - "findnext32i64 (fonction)"
  - "tfindnext64i32 (fonction)"
  - "_tfindnext64i32 (fonction)"
  - "_findnext (fonction)"
  - "findnext64i32 (fonction)"
  - "_tfindnext (fonction)"
  - "findnext32 (fonction)"
  - "tfindnext32 (fonction)"
  - "_findnext32 (fonction)"
  - "_tfindnext32i64 (fonction)"
  - "_wfindnext (fonction)"
  - "tfindnext (fonction)"
  - "_findnext64 (fonction)"
  - "findnext64 (fonction)"
  - "_findnext64i32 (fonction)"
  - "wfindnext32i64 (fonction)"
  - "findnext (fonction)"
  - "wfindnext32 (fonction)"
  - "_wfindnext64i32 (fonction)"
  - "findnexti64 (fonction)"
  - "_wfindnext64 (fonction)"
  - "_findnext32i64 (fonction)"
  - "_findnexti64 (fonction)"
  - "_tfindnext64 (fonction)"
  - "wfindnext64i32 (fonction)"
  - "tfindnexti64 (fonction)"
  - "wfindnext64 (fonction)"
  - "wfindnext (fonction)"
  - "tfindnext64 (fonction)"
  - "_wfindnext32 (fonction)"
  - "tfindnext32i64 (fonction)"
  - "_tfindnexti64 (fonction)"
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherchez le nom suivant, le cas échéant, qui correspond à l'argument `filespec` dans un appel précédent à [\_findfirst](../../c-runtime-library/reference/findfirst-functions.md), puis modifiez le contenu de la structure `fileinfo` en conséquence.  
  
## Syntaxe  
  
```  
int _findnext(  
   intptr_t handle,  
   struct _finddata_t *fileinfo   
);  
int _findnext32(  
   intptr_t handle,  
   struct _finddata32_t *fileinfo   
);  
int _findnext64(  
   intptr_t handle,  
   struct __finddata64_t *fileinfo   
);  
int _findnexti64(  
   intptr_t handle,  
   struct __finddatai64_t *fileinfo   
);  
int _findnext32i64(  
   intptr_t handle,  
   struct _finddata32i64_t *fileinfo   
);  
int _findnext64i32(  
   intptr_t handle,  
   struct _finddata64i32_t *fileinfo   
);  
int _wfindnext(  
   intptr_t handle,  
   struct _wfinddata_t *fileinfo   
);  
int _wfindnext32(  
   intptr_t handle,  
   struct _wfinddata32_t *fileinfo   
);  
int _wfindnext64(  
   intptr_t handle,  
   struct _wfinddata64_t *fileinfo   
);  
int _wfindnexti64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext32i64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext64i32(  
   intptr_t handle,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### Paramètres  
 `handle`  
 Recherchez le descripteur retourné par un appel précédent à `_findfirst`.  
  
 `fileinfo`  
 Mémoire tampon de l'Information fichier.  
  
## Valeur de retour  
 En cas de réussite, retourne 0.  Sinon, retourne – 1 et affecte `errno` à une valeur qui indique la nature de l'erreur.  Les codes d'erreur possibles sont répertoriés dans le tableau suivant.  
  
 `EINVAL`  
 Paramètre non valide: `fileinfo` était `NULL`.  Ou, le système d'exploitation a retourné une erreur inattendue.  
  
 `ENOENT`  
 Plus aucun fichierscorrespondant n'a pu être détecté.  
  
 `ENOMEM`  
 Mémoire insuffisante ou la longueur du nom de fichier a dépassé `MAX_PATH`.  
  
 Si un paramètre non valide a été passé, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## Notes  
 Vous devez appeler [\_findclose](../../c-runtime-library/reference/findclose.md) au terme de l'utilisation de la fonction `_findfirst` ou de la fonction `_findnext` \(ou toutes variantes\).  Cela libère les ressources utilisées par ces fonctions dans votre application.  
  
 Les variations de ces fonctions avec le préfixe `w` sont des versions de caractères larges ; sinon, elles sont identiques aux fonctions codées sur un octet correspondantes.  
  
 Les variations de ces fonctions prennent en charge les types d'heure 32 bits ou 64 bits et les fichiers de taille 32 bits ou 64 bits.  Le premier suffixe numérique \(`32` ou `64`\) indique la taille du type de temps utilisé ; le deuxième suffixe est `i32` ou `i64`, qui indique si la taille du fichier est représentée comme un entier 32 bits ou 64 bits.  Pour plus d'informations sur quelles versions prennent en charge les types d'heure 32 bits et 64 bits et les tailles de fichiers, consultez le tableau suivant.  Les variations qui utilisent un type d'heure 64 bits permettent aux dates de création FILE d'être exprimées jusqu'à 23:59:59, le 31 décembre, 3000, UTC ; alors que celles utilisant les types d'heure 32 bits uniquement représentent les dates jusqu'à 19:14:07, le 18 janvier, 2038, UTC.  Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour ces deux fonctions.  
  
 À moins d'avoir une raison particulière d'utiliser les versions qui spécifient la taille de temps explicitement, utilisez `_findnext` ou `_wfindnext` ou, si vous avez besoin de supporter des tailles de fichier supérieures à 3Go , utilisez `_findnexti64` ou `_wfindnexti64`.  Toutes ces fonctions utilisent le type d'heure 64 bits.  Dans les versions antérieures, ces fonctions ont utilisé le type d'heure 32 bits.  S'il s'agit d'une modification importante pour une application, vous pouvez définir `_USE_32BIT_TIME_T` pour obtenir le comportement antérieur.  Si `_USE_32BIT_TIME_T` est défini, `_findnext`, `_finnexti64` et leurs versions correspondantes Unicode utilisent une heure 32 bits.  
  
### Type d'Heure et Variation du Type de Longueur de Fichier de \_findnext  
  
|Fonctions|`_USE_32BIT_TIME_T` défini?|Type de Temps|Type de taille de fichier|  
|---------------|---------------------------------|-------------------|-------------------------------|  
|`_findnext`, `_wfindnext`|Non défini|64 bits|32 bits|  
|`_findnext`, `_wfindnext`|\(défini par\)|32 bits|32 bits|  
|`_findnext32`, `_wfindnext32`|Non affecté par la définition de macro|32 bits|32 bits|  
|`_findnext64`, `_wfindnext64`|Non affecté par la définition de macro|64 bits|64 bits|  
|`_findnexti64`, `_wfindnexti64`|Non défini|64 bits|64 bits|  
|`_findnexti64`, `_wfindnexti64`|\(défini par\)|32 bits|64 bits|  
|`_findnext32i64`, `_wfindnext32i64`|Non affecté par la définition de macro|32 bits|64 bits|  
|`_findnext64i32`, `_wfindnext64i32`|Non affecté par la définition de macro|64 bits|32 bits|  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tfindnext`|`_findnext`|`_findnext`|`_wfindnext`|  
|`_tfindnext32`|`_findnext32`|`_findnext32`|`_wfindnext32`|  
|`_tfindnext64`|`_findnext64`|`_findnext64`|`_wfindnext64`|  
|`_tfindnexti64`|`_findnexti64`|`_findnexti64`|`_wfindnexti64`|  
|`_tfindnext32i64`|`_findnext32i64`|`_findnext32i64`|`_wfindnext32i64`|  
|`_tfindnext64i32`|`_findnext64i32`|`_findnext64i32`|`_wfindnext64i32`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_findnext`|\<io.h,\>|  
|`_findnext32`|\<io.h,\>|  
|`_findnext64`|\<io.h,\>|  
|`_findnexti64`|\<io.h,\>|  
|`_findnext32i64`|\<io.h,\>|  
|`_findnext64i32`|\<io.h,\>|  
|`_wfindnext`|\<io.h\> ou \<wchar.h\>|  
|`_wfindnext32`|\<io.h\> ou \<wchar.h\>|  
|`_wfindnext64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindnexti64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindnext32i64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindnext64i32`|\<io.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Appels système](../../c-runtime-library/system-calls.md)   
 [Fonctions de recherche de nom de fichier](../../c-runtime-library/filename-search-functions.md)