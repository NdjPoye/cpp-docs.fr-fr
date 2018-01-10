---
title: _access_s, _waccess_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access_s
- _waccess_s
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
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs: C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f562d62f3edb1f09fe6d7ebe7b509411ad2dc8c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s
Détermine les autorisations de lecture/écriture de fichier. Il s’agit d’une version de [_access, _waccess](../../c-runtime-library/reference/access-waccess.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Chemin du répertoire ou du fichier.  
  
 `mode`  
 Paramètre d'autorisation.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne 0 si le fichier a le mode donné. La fonction retourne un code d’erreur si le fichier nommé n’existe pas ou qu’il est inaccessible dans le mode donné. Dans ce cas, la fonction retourne un code d’erreur de l’ensemble suivant et définit également `errno` sur la même valeur.  
  
 `EACCES`  
 Accès refusé. Le paramètre d’autorisation du fichier n’autorise pas l’accès spécifié.  
  
 `ENOENT`  
 Chemin ou nom de fichier introuvable.  
  
 `EINVAL`  
 Paramètre non valide.  
  
 Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Quand elle est utilisée avec des fichiers, la fonction `_access_s` détermine si le fichier spécifié existe et est accessible conformément à la valeur de `mode`. Quand elle est utilisée avec des répertoires, `_access_s` détermine uniquement si le répertoire spécifié existe. Dans [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] et les systèmes d’exploitation ultérieurs, tous les répertoires sont accessibles en lecture et écriture.  
  
|Valeur du mode|Test réalisé sur le fichier|  
|----------------|---------------------|  
|00|Existence uniquement.|  
|02|Autorisation d’écriture.|  
|04|Autorisation de lecture.|  
|06|Autorisations de lecture et d’écriture.|  
  
 L’autorisation de lecture ou d’écriture dans le fichier n’est pas suffisante pour assurer la possibilité d’ouvrir un fichier. Par exemple, si un fichier est verrouillé par un autre processus, il peut être inaccessible même si `_access_s` retourne la valeur 0.  
  
 `_waccess_s` est une version à caractères larges de `_access_s`, où l’argument `path` de `_waccess_s` est une chaîne à caractères larges. Sinon, `_waccess_s` et `_access_s` se comportent de la même façon.  
  
 Ces fonctions valident leurs paramètres. Si `path` est `NULL` ou que `mode` ne spécifie pas de mode valide, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_access_s`|\<io.h>|\<errno.h>|  
|`_waccess_s`|\<wchar.h> ou \<io.h>|\<errno.h>|  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise `_access_s` pour vérifier si le fichier nommé crt_access_s.c existe et si l’écriture est autorisée.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
```Output  
File crt_access_s.c exists.  
File crt_access_s.c does not have write permission.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)