---
title: "_splitpath_s, _wsplitpath_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath_s"
  - "_splitpath_s"
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
  - "_wsplitpath_s"
  - "splitpath_s"
  - "_splitpath_s"
  - "wsplitpath_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_splitpath_s (fonction)"
  - "_wsplitpath_s (fonction)"
  - "noms de chemin d'accès"
  - "noms de chemins d'accès"
  - "splitpath_s (fonction)"
  - "wsplitpath_s (fonction)"
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _splitpath_s, _wsplitpath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Divise un nom de chemin d'accès en ses composants élémentaires.  Il s'agit de versions de [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### Paramètres  
 \[in\] `path`  
 Chemin d'accès complet.  
  
 \[out\] `drive`  
 Lettre de lecteur, suivi de deux\-points \(`:`\).  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin de la lettre de lecteur.  
  
 \[in\] `driveNumberOfElements`  
 La taille de la mémoire tampon `drive` en caractères codés sur un octet ou en caractères larges.  Si `drive` is `NULL`, cette valeur doit être 0.  
  
 \[out\] `dir`  
 Chemin d'accès au répertoire, invluant la barre oblique finale.  Des barres obliques \( `/` \), les barres obliques inverses \( `\` \), ou les deux peuvent être utilisées.  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin du chemin d'accès.  
  
 \[in\] `dirNumberOfElements`  
 La taille de la mémoire tampon `dir` en caractères codés sur un octet ou en caractères larges.  Si `dir` is `NULL`, cette valeur doit être 0.  
  
 \[out\] `fname`  
 Nom du fichier de base \(sans l'extension\).  Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin du nom du fichier.  
  
 \[in\] `nameNumberOfElements`  
 La taille de la mémoire tampon `fname` en caractères codés sur un octet ou en caractères larges.  Si `fname` is `NULL`, cette valeur doit être 0.  
  
 \[out\] `ext`  
 Extension du nom de fichier, y compris le principal point \(**.**\)\). Vous pouvez passer `NULL` pour ce paramètre si vous n'avez pas besoin de l'extension de nom de fichier.  
  
 \[in\] `extNumberOfElements`  
 La taille de la mémoire tampon `ext` en caractères codés sur un octet ou en caractères larges.  Si `ext` is `NULL`, cette valeur doit être 0.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|Condition|Valeur de retour|  
|---------------|----------------------|  
|`path` est `NULL`|`EINVAL`|  
|`drive` est `NULL`, `driveNumberOfElements` est non NULL|`EINVAL`|  
|`drive` est non\-`NULL`, `driveNumberOfElements` est NULL|`EINVAL`|  
|`dir` est `NULL`, `dirNumberOfElements` est non NULL|`EINVAL`|  
|`dir` est non\-`NULL`, `dirNumberOfElements` est NULL|`EINVAL`|  
|`fname` est `NULL`, `nameNumberOfElements` est non NULL|`EINVAL`|  
|`fname` est non\-`NULL`, `nameNumberOfElements` est NULL|`EINVAL`|  
|`ext` est `NULL`, `extNumberOfElements` est non NULL|`EINVAL`|  
|`ext` est non\-`NULL`, `extNumberOfElements` est NULL|`EINVAL`|  
  
 Si l'une de ces conditions d'erreur ci\-dessus se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `EINVAL`.  
  
 Si l'une au moins des mémoires tampons est trop petite pour retenire le résultat, ces fonctions effacent toutes les mémoires tampons et les remplacent pas des chaînes vides, affectent `errno` à `ERANGE`, et retournent `ERANGE`.  
  
## Notes  
 La fonction `_splitpath_s` divise un chemin d'accès par ses quatre composants.  `_splitpath_s`  gère automatiquement des arguments de chaîne de caractères multi\-octets comme appropriés, en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation.  `_wsplitpath_s` est une version à large caractères de `_splitpath_s`; les arguments de `_``wsplitpath_s` `` sont des chaînes de caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Chaque composant du chemin d'accès complet est stockée dans une mémoire tampon distincte ; les constantes explicites `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, et `_MAX_EXT` \(définies dans STDLIB.H\) spécifient la taille maximale autorisée pour chaque composant de fichier.  Les composants des fichiers de dimensions supérieures aux constantes explicites correspondantes engendrent la corruption des données des segments de mémoires.  
  
 Le tableau suivant répertorie les valeurs des constantes explicites.  
  
|Nom|Valeur|  
|---------|------------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 Si le chemin complet ne contient aucun composant \(par exemple, un nom de fichier\), `_splitpath_s` affecte une chaîne vide à la mémoire tampon correspondante.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h\>|  
|`_wsplitpath_s`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple pour [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)