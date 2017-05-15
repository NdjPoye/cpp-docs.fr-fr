---
title: _access, _waccess | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: d0968ec14a43cfbbf1169f34ac929435787bc349
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="access-waccess"></a>_access, _waccess
Détermine si un fichier est en lecture seule ou non. Des versions plus sécurisées sont disponibles. Consultez [_access_s, _waccess_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Chemin du répertoire ou du fichier.  
  
 `mode`  
 Attribut de lecture/écriture.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne 0 si le fichier a le mode donné. La fonction retourne -1 si le fichier nommé n’existe pas ou n’a pas le mode donné ; Dans ce cas, `errno` est défini comme indiqué dans le tableau suivant.  
  
 `EACCES`  
 Accès refusé : le paramètre d’autorisation du fichier n’autorise pas l’accès spécifié.  
  
 `ENOENT`  
 Chemin ou nom de fichier introuvable.  
  
 `EINVAL`  
 Paramètre non valide.  
  
 Pour plus d’informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Quand elle est utilisée avec des fichiers, la fonction `_access` détermine si le répertoire ou fichier spécifié existe et a les attributs spécifiés par la valeur de `mode`. Quand elle est utilisée avec des répertoires, `_access` détermine uniquement si le répertoire spécifié existe ; dans [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] et les systèmes d’exploitation ultérieurs, tous les répertoires sont accessibles en lecture et écriture.  
  
|Valeur `mode`|Test réalisé sur le fichier|  
|------------------|---------------------|  
|00|Existence uniquement|  
|02|En écriture seule|  
|04|Lecture seule|  
|06|Opérations de lecture et d’écriture|  
  
 Cette fonction vérifie uniquement si le fichier et le répertoire sont en lecture seule ou non ; elle ne vérifie pas les paramètres de sécurité du système de fichiers. Pour cela, vous avez besoin d’un jeton d’accès. Pour plus d’informations sur la sécurité du système de fichiers, consultez [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909) (Jetons d’accès). Il existe une classe ATL pour fournir cette fonctionnalité ; consultez [CAccessToken, classe](../../atl/reference/caccesstoken-class.md).  
  
 `_waccess` est une version à caractères larges de `_access` ; l'argument `path` de `_waccess` est une chaîne à caractères larges. Sinon, `_waccess` et `_access` se comportent de la même façon.  
  
 Cette fonction valide ses paramètres. Si `path` est `NULL` ou que `mode` ne spécifie pas de mode valide, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction définit `errno` avec la valeur `EINVAL` et retourne -1.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-têtes facultatifs|  
|-------------|---------------------|----------------------|  
|`_access`|\<io.h>|\<errno.h>|  
|`_waccess`|\<wchar.h> ou \<io.h>|\<errno.h>|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise `_access` pour vérifier si le fichier nommé crt_ACCESS.C existe et si l’écriture est autorisée.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
```Output  
File crt_ACCESS.C exists.  
File crt_ACCESS.C does not have write permission.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)
