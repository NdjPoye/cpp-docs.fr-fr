---
title: _umask_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 5c8efcdf5d3f44a6cd3bbcc39f2a98e3659c95ab
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="umasks"></a>_umask_s
Définit le masque d’autorisation de fichier par défaut. Version de [_umask](../../c-runtime-library/reference/umask.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `mode`  
 Paramètre d’autorisation par défaut.  
  
 [out] `oldMode`  
 Valeur précédente du paramètre d’autorisation.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un code d’erreur si `Mode` ne spécifie pas de mode valide ou si le pointeur `pOldMode` a la valeur `NULL`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`mode`|`pOldMode`|**Valeur de retour**|**Contenu de**  `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|indifférent|`NULL`|`EINVAL`|non modifié|  
|mode non valide|indifférent|`EINVAL`|non modifié|  
  
 Si l’une des conditions ci-dessus se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, `_umask_s` retourne `EINVAL` et définit `errno` à `EINVAL`.  
  
## <a name="remarks"></a>Remarques  
 Le `_umask_s` fonction définit le masque d’autorisation de fichier du processus en cours pour le mode spécifié par `mode`. Le masque d’autorisation de fichier modifie le paramètre d’autorisation des nouveaux fichiers créés par `_creat`, `_open` ou `_sopen`. Si un bit a la valeur 1 dans le masque, le bit correspondant dans la valeur d’autorisation demandée du fichier prend la valeur 0 (non autorisé). Si un bit a la valeur 0 dans le masque, le bit correspondant est inchangé. Le paramètre d’autorisation d’un nouveau fichier n’est pas défini tant qu’il n’est pas fermé pour la première fois.  
  
 L’expression d’entier `pmode` contient l’une des constantes manifestes suivantes (ou les deux), définies dans SYS\STAT.H :  
  
 `_S_IWRITE`  
 Écriture autorisée.  
  
 `_S_IREAD`  
 Lecture autorisée.  
  
 `_S_IREAD | _S_IWRITE`  
 Lecture et écriture autorisées.  
  
 Quand les deux constantes sont transmises, elles sont jointes avec l’opérateur OR au niveau du bit ( `|` ). Si l’argument `mode` a la valeur `_S_IREAD`, la lecture n’est pas autorisée (le fichier est en écriture seule). Si l’argument `mode` a la valeur `_S_IWRITE`, l’écriture n’est pas autorisée (le fichier est en lecture seule). Par exemple, si le bit d’écriture est défini dans le masque, les nouveaux fichiers sont en lecture seule. Notez qu’avec les systèmes d’exploitation MS-DOS et Windows, tous les fichiers sont lisibles ; il est impossible d’accorder une autorisation en écriture seule. Par conséquent, le fait définir le bit de lecture avec `_umask_s` n’a aucun effet sur les modes du fichier.  
  
 Si `pmode` n’est pas une combinaison de l’une des constantes manifestes ou incorpore un autre ensemble de constantes, la fonction les ignore simplement.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_umask_s`|\<io.h>, \<sys/stat.h> et \<sys/types.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)
