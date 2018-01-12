---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath_s
- _splitpath_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs: C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6cfb2d72b728b64aeb00c3b8437f9c47e02fb813
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s
Divise un nom de chemin en composants. Ces versions de [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 [in] `path`  
 Chemin complet.  
  
 [out] `drive`  
 Lettre de lecteur suivie de deux-points (`:`). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin de la lettre de lecteur.  
  
 [in] `driveNumberOfElements`  
 Taille de la mémoire tampon `drive` en caractères larges ou codés sur un octet. Si `drive` a la valeur `NULL`, cette valeur doit être égale à 0.  
  
 [out] `dir`  
 Chemin de répertoire incluant une barre oblique de fin. Il est possible d’utiliser des barres obliques ( `/` ), des barres obliques inverses ( `\` ) ou les deux à la fois. Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin du chemin de répertoire.  
  
 [in] `dirNumberOfElements`  
 Taille de la mémoire tampon `dir` en caractères larges ou codés sur un octet. Si `dir` a la valeur `NULL`, cette valeur doit être égale à 0.  
  
 [out] `fname`  
 Nom de fichier de base (sans extension). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin du nom de fichier.  
  
 [in] `nameNumberOfElements`  
 Taille de la mémoire tampon `fname` en caractères larges ou codés sur un octet. Si `fname` a la valeur `NULL`, cette valeur doit être égale à 0.  
  
 [out] `ext`  
 Extension de nom de fichier incluant le point de début (**.**). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin de l’extension de nom de fichier.  
  
 [in] `extNumberOfElements`  
 Taille de la mémoire tampon `ext` en caractères larges ou codés sur un octet. Si `ext` a la valeur `NULL`, cette valeur doit être égale à 0.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|Condition|Valeur de retour|  
|---------------|------------------|  
|`path` a la valeur `NULL`.|`EINVAL`|  
|`drive` a la valeur `NULL`, `driveNumberOfElements` est différent de zéro|`EINVAL`|  
|`drive` n’a pas la valeur `NULL`, `driveNumberOfElements` est égal à zéro|`EINVAL`|  
|`dir` a la valeur `NULL`, `dirNumberOfElements` est différent de zéro|`EINVAL`|  
|`dir` n’a pas la valeur `NULL`, `dirNumberOfElements` est égal à zéro|`EINVAL`|  
|`fname` a la valeur `NULL`, `nameNumberOfElements` est différent de zéro|`EINVAL`|  
|`fname` n’a pas la valeur `NULL`, `nameNumberOfElements` est égal à zéro|`EINVAL`|  
|`ext` a la valeur `NULL`, `extNumberOfElements` est différent de zéro|`EINVAL`|  
|`ext` n’a pas la valeur `NULL`, `extNumberOfElements` est égal à zéro|`EINVAL`|  
  
 Si l’une des conditions ci-dessus se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
 Si la taille de l’une des mémoires tampons ne suffit pas à contenir le résultat, ces fonctions remplacent le contenu de toutes les mémoires tampons par des chaînes vides, affectent à `errno` la valeur `ERANGE` et retournent `ERANGE`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_splitpath_s` divise un chemin en quatre composants. `_splitpath_s` gère automatiquement les arguments de chaîne de caractères multioctets si nécessaire, en identifiant les séquences de caractères multioctets en fonction de la page de codes multioctets en cours d’utilisation. `_wsplitpath_s` est une version à caractères larges de `_splitpath_s` ; les arguments de `_wsplitpath_s` sont des chaînes à caractères larges. Sinon, ces fonctions se comportent de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Chaque composant du chemin complet est stocké dans une mémoire tampon distincte ; les constantes manifestes `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` et `_MAX_EXT` (définies dans STDLIB.H) spécifient la taille maximale autorisée de chaque composant de fichier. Les composants de fichier dont la taille dépasse celle des constantes manifestes correspondantes occasionnent une altération du tas.  
  
 Le tableau suivant répertorie les valeurs des constantes manifestes.  
  
|Name|Value|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Si le chemin complet ne contient pas de composant (par exemple, un nom de fichier), `_splitpath_s` affecte une chaîne vide à la mémoire tampon correspondante.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; celles-ci peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h>|  
|`_wsplitpath_s`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)