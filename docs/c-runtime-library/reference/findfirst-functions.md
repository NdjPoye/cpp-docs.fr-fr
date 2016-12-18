---
title: "_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64 | Microsoft Docs"
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
  - "_findfirst"
  - "_wfindfirst"
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
  - "findfirst32i64"
  - "wfindfirst32i64"
  - "tfindfirst64"
  - "_findfirst64i32"
  - "_wfindfirst32i64"
  - "_wfindfirsti64"
  - "wfindfirst"
  - "_tfindfirsti64"
  - "findfirst32"
  - "_tfindfirst32"
  - "_findfirsti64"
  - "findfirst"
  - "wfindfirst64"
  - "wfindfirst32"
  - "tfindfirst32"
  - "_wfindfirst64i32"
  - "findfirst64i32"
  - "tfindfirst64i32"
  - "_wfindfirst"
  - "findfirsti64"
  - "_findfirst32i64"
  - "wfindfirst64i32"
  - "_wfindfirst32"
  - "_findfirst32"
  - "_tfindfirst32i64"
  - "tfindfirst"
  - "_tfindfirst64i32"
  - "findfirst64"
  - "_tfindfirst"
  - "_findfirst64"
  - "_tfindfirst64"
  - "tfindfirst32i64"
  - "_findfirst"
  - "_wfindfirst64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tfindfirst64, fonction"
  - "_wfindfirst64i32, fonction"
  - "_wfindfirst32i64, fonction"
  - "wfindfirst32, fonction"
  - "_findfirst, fonction"
  - "wfindfirst64, fonction"
  - "_wfindfirst, fonction"
  - "_findfirst64i32, fonction"
  - "wfindfirst, fonction"
  - "_findfirst64, fonction"
  - "tfindfirst32, fonction"
  - "_tfindfirst64i32, fonction"
  - "findfirst, fonction"
  - "findfirst32i64, fonction"
  - "tfindfirst64, fonction"
  - "_tfindfirst32, fonction"
  - "tfindfirst32i64, fonction"
  - "tfindfirst64i32, fonction"
  - "_wfindfirsti64, fonction"
  - "_findfirst32i64, fonction"
  - "findfirst32, fonction"
  - "findfirsti64, fonction"
  - "findfirst64i32, fonction"
  - "tfindfirsti64, fonction"
  - "tfindfirst, fonction"
  - "_wfindfirst32, fonction"
  - "wfindfirsti64, fonction"
  - "_tfindfirsti64, fonction"
  - "_tfindfirst, fonction"
  - "_tfindfirst32i64, fonction"
  - "findfirst64, fonction"
  - "_findfirst32, fonction"
  - "_findfirsti64, fonction"
  - "wfindfirst32i64, fonction"
  - "wfindfirst64i32, fonction"
  - "_wfindfirst64, fonction"
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des informations à propos de la première instance d'un nom de fichier correspondant au fichier spécifié dans l'argument `filespec`.  
  
## Syntaxe  
  
```  
intptr_t _findfirst(  
   const char *filespec,  
   struct _finddata_t *fileinfo   
);  
intptr_t _findfirst32(  
   const char *filespec,  
   struct _finddata32_t *fileinfo   
);  
intptr_t _findfirst64(  
   const char *filespec,  
   struct _finddata64_t *fileinfo   
);  
intptr_t _findfirsti64(  
   const char *filespec,  
   struct _finddatai64_t *fileinfo   
);  
intptr_t _findfirst32i64(  
   const char *filespec,  
   struct _finddata32i64_t *fileinfo   
);  
intptr_t _findfirst64i32(  
   const char *filespec,  
   struct _finddata64i32_t *fileinfo   
);  
intptr_t _wfindfirst(  
   const wchar_t *filespec,  
   struct _wfinddata_t *fileinfo   
);  
intptr_t _wfindfirst32(  
   const wchar_t *filespec,  
   struct _wfinddata32_t *fileinfo   
);  
intptr_t _wfindfirst64(  
   const wchar_t *filespec,  
   struct _wfinddata64_t *fileinfo   
);  
intptr_t _wfindfirsti64(  
   const wchar_t *filespec,  
   struct _wfinddatai64_t *fileinfo   
);  
intptr_t _wfindfirst32i64(  
   const wchar_t *filespec,  
   struct _wfinddata32i64_t *fileinfo   
);  
intptr_t _wfindfirst64i32(  
   const wchar_t *filespec,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### Paramètres  
 `filespec`  
 Spécification du fichier cible \(peut comprendre des caractères génériques\).  
  
 `fileinfo`  
 Mémoire tampon de l'Information fichier.  
  
## Valeur de retour  
 En cas de réussite, `_findfirst` retourne un descripteur unique de recherche qui identifie le fichier ou l'ensemble de fichiers qui correspondent à la spécification `filespec`, qui peut être utilisée dans l'appel suivant à [\_findnext](../../c-runtime-library/reference/findnext-functions.md) ou à `_findclose`.  Sinon, `_findfirst` retourne – 1 et affecte `errno` à l'une des valeurs suivantes.  
  
 `EINVAL`  
 Paramètre non valide: `filespec` ou `fileinfo` était `NULL`.  Ou, le système d'exploitation a retourné une erreur inattendue.  
  
 `ENOENT`  
 Spécification de fichiers qui ne peut pas être mise en correspondance.  
  
 `ENOMEM`  
 Mémoire insuffisante.  
  
 `EINVAL`  
 Spécification de nom de fichier invalide ou le nom du fichier donné est plus grand que `MAX_PATH`.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Si un paramètre non valide a été passé, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## Notes  
 Vous devez appeler [\_findclose](../../c-runtime-library/reference/findclose.md) au terme de l'utilisation de la fonction `_findfirst` ou de la fonction `_findnext` \(ou toutes variantes\).  Cela libère les ressources utilisées par ces fonctions dans votre application.  
  
 Les variations de ces fonctions qui ont le préfixe `w` sont des versions de caractères larges ; sinon, elles sont identiques aux fonctions codées sur un octet correspondantes.  
  
 Les variations de ces fonctions prennent en charge les types d'heure 32 bits ou 64 bits et les fichiers de taille 32 bits ou 64 bits.  Le premier suffixe numérique \(`32` ou `64`\) indique la taille du type de temps utilisé ; le deuxième suffixe est `i32` ou `i64`, et indique si la taille du fichier est représentée comme un entier 32 bits ou 64 bits.  Pour plus d'informations sur quelles versions prennent en charge les types d'heure 32 bits et 64 bits et les tailles de fichiers, consultez le tableau suivant.  Le suffixe `i32` ou `i64` est omis si c'est le même que la taille du type d'heure, donc `_findfirst64` prend également en charge les fichiers de longueur 64 bits et `_findfirst32` prend en charge les fichiers de longueur 32 bits..  
  
 Ces fonctions utilisent des formes variées de la structure `_finddata_t` pour le paramètre `fileinfo`.  Pour plus d'informations sur la structure, consultez [Fonctions de recherche de nom de fichier](../../c-runtime-library/filename-search-functions.md).  
  
 Les variations qui utilisent un type d'heure 64 bits permettent aux dates de création de fichier d'être exprimées à 23h59 : 59, le 31 décembre, 3000, UTC.  Ceux qui utilisent les types d'heure 32 bits représentent les dates uniquement à 19h14:07 Le 18 janvier, 2038, les valeurs UTC.  Minuit, le 1er janvier 1970, est la limite inférieure de la plage de dates pour ces deux fonctions.  
  
 À moins d'avoir une raison particulière d'utiliser les versions qui spécifient la taille de temps explicitement, utilisez `_findfirst` ou `_wfindfirst` ou, si vous avez besoin de supporter des tailles de fichier supérieures à 3Go , utilisez `_findfirsti64` ou `_wfindfirsti64`.  Toutes ces fonctions utilisent le type d'heure 64 bits.  Dans les versions antérieures, ces fonctions ont utilisé le type d'heure 32 bits.  S'il s'agit d'une modification importante pour une application, vous pouvez définir `_USE_32BIT_TIME_T` pour revenir au comportement antérieur.  Si `_USE_32BIT_TIME_T` est défini, `_findfirst`, `_finfirsti64` et leurs versions correspondantes Unicode utilisent une heure 32 bits.  
  
### Type d'Heure et Variation du Type de Longueur de Fichier de \_findfirst  
  
|Fonctions|`_USE_32BIT_TIME_T` défini?|Type de Temps|Type de taille de fichier|  
|---------------|---------------------------------|-------------------|-------------------------------|  
|`_findfirst`, `_wfindfirst`|Non défini|64 bits|32 bits|  
|`_findfirst`, `_wfindfirst`|\(défini par\)|32 bits|32 bits|  
|`_findfirst32`, `_wfindfirst32`|Non affecté par la définition de macro|32 bits|32 bits|  
|`_findfirst64`, `_wfindfirst64`|Non affecté par la définition de macro|64 bits|64 bits|  
|`_findfirsti64`, `_wfindfirsti64`|Non défini|64 bits|64 bits|  
|`_findfirsti64`, `_wfindfirsti64`|\(défini par\)|32 bits|64 bits|  
|`_findfirst32i64`, `_wfindfirst32i64`|Non affecté par la définition de macro|32 bits|64 bits|  
|`_findfirst64i32`, `_wfindfirst64i32`|Non affecté par la définition de macro|64 bits|32 bits|  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tfindfirst`|`_findfirst`|`_findfirst`|`_wfindfirst`|  
|`_tfindfirst32`|`_findfirst32`|`_findfirst32`|`_wfindfirst32`|  
|`_tfindfirst64`|`_findfirst64`|`_findfirst64`|`_wfindfirst64`|  
|`_tfindfirsti64`|`_findfirsti64`|`_findfirsti64`|`_wfindfirsti64`|  
|`_tfindfirst32i64`|`_findfirst32i64`|`_findfirst32i64`|`_wfindfirst32i64`|  
|`_tfindfirst64i32`|`_findfirst64i32`|`_findfirst64i32`|`_wfindfirst64i32`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_findfirst`|\<io.h,\>|  
|`_findfirst32`|\<io.h,\>|  
|`_findfirst64`|\<io.h,\>|  
|`_findfirsti64`|\<io.h,\>|  
|`_findfirst32i64`|\<io.h,\>|  
|`_findfirst64i32`|\<io.h,\>|  
|`_wfindfirst`|\<io.h\> ou \<wchar.h\>|  
|`_wfindfirst32`|\<io.h\> ou \<wchar.h\>|  
|`_wfindfirst64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindfirsti64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindfirst32i64`|\<io.h\> ou \<wchar.h\>|  
|`_wfindfirst64i32`|\<io.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [System::IO::DirectoryInfo::GetFiles](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)  
  
## Voir aussi  
 [Appels système](../../c-runtime-library/system-calls.md)   
 [Fonctions de recherche de nom de fichier](../../c-runtime-library/filename-search-functions.md)