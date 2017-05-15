---
title: _splitpath, _wsplitpath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: bbd6a163df9daf8e699f3ecf52325786fe89d8ea
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath
Divisent un nom de chemin en composants. Il existe des versions plus sécurisées de ces fonctions. Consultez [_searchenv_s, _wsearchenv_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Chemin complet.  
  
 `drive`  
 Lettre de lecteur suivie de deux-points (`:`). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin de la lettre de lecteur.  
  
 `dir`  
 Chemin de répertoire incluant une barre oblique de fin. Il est possible d’utiliser des barres obliques ( `/` ), des barres obliques inverses ( `\` ) ou les deux à la fois. Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin du chemin de répertoire.  
  
 `fname`  
 Nom de fichier de base (sans extension). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin du nom de fichier.  
  
 `ext`  
 Extension de nom de fichier incluant le point de début (`.`). Vous pouvez passer la valeur `NULL` pour ce paramètre si vous n’avez pas besoin de l’extension de nom de fichier.  
  
## <a name="remarks"></a>Notes  
 La fonction `_splitpath` divise un chemin en quatre composants. `_splitpath` gère automatiquement les arguments de chaîne de caractères multioctets si nécessaire, en identifiant les séquences de caractères multioctets en fonction de la page de codes multioctets en cours d’utilisation. `_wsplitpath` est une version à caractères larges de `_splitpath` ; les arguments de `_wsplitpath` sont des chaînes à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
 **Remarque relative à la sécurité** Ces fonctions sont exposées à une menace potentielle liée à un problème de dépassement de mémoire tampon. Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795). Il existe des versions plus sécurisées de ces fonctions. Consultez [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Chaque composant du chemin complet est stocké dans une mémoire tampon distincte ; les constantes manifestes `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` et `_MAX_EXT` (définies dans STDLIB.H) spécifient la taille maximale de chaque composant de fichier. Les composants de fichier dont la taille dépasse celle des constantes manifestes correspondantes occasionnent une altération du tas.  
  
 Chaque mémoire tampon doit être aussi volumineuse que sa constante manifeste correspondante pour éviter un possible dépassement de mémoire tampon.  
  
 Le tableau suivant répertorie les valeurs des constantes manifestes.  
  
|Nom|Valeur|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Si le chemin complet ne contient pas de composant (par exemple, un nom de fichier), `_splitpath` affecte des chaînes vides aux mémoires tampons correspondantes.  
  
 Vous pouvez passer la valeur `NULL` à `_splitpath` pour tout paramètre autre que `path` dont vous n’avez pas besoin.  
  
 Si `path` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h>|  
|`_wsplitpath`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)
