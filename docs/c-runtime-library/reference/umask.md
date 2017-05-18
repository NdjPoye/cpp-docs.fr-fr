---
title: _umask | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask
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
- _umask
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
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
ms.openlocfilehash: f2ad9c75caa5f3816ab4791dc4e67cb7937bfad4
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="umask"></a>_umask
Définit le masque d’autorisation de fichier par défaut. Une version plus sécurisée de cette fonction est disponible. Consultez [_umask_s](../../c-runtime-library/reference/umask-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pmode`  
 Paramètre d’autorisation par défaut.  
  
## <a name="return-value"></a>Valeur de retour  
 `_umask` retourne la valeur précédente de `pmode`. Aucun retour d'erreur.  
  
## <a name="remarks"></a>Remarques  
 Le `_umask` fonction définit le masque d’autorisation de fichier du processus en cours pour le mode spécifié par `pmode`. Le masque d’autorisation de fichier modifie le paramètre d’autorisation des nouveaux fichiers créés par `_creat`, `_open` ou `_sopen`. Si un bit a la valeur 1 dans le masque, le bit correspondant dans la valeur d’autorisation demandée du fichier prend la valeur 0 (non autorisé). Si un bit a la valeur 0 dans le masque, le bit correspondant est inchangé. Le paramètre d’autorisation d’un nouveau fichier n’est pas défini tant qu’il n’est pas fermé pour la première fois.  
  
 L’expression d’entier `pmode` contient l’une des constantes manifestes suivantes (ou les deux), définies dans SYS\STAT.H :  
  
 `_S_IWRITE`  
 Écriture autorisée.  
  
 `_S_IREAD`  
 Lecture autorisée.  
  
 `_S_IREAD | _S_IWRITE`  
 Lecture et écriture autorisées.  
  
 Quand les deux constantes sont transmises, elles sont jointes avec l’opérateur OR au niveau du bit ( `|` ). Si l’argument `pmode` a la valeur `_S_IREAD`, la lecture n’est pas autorisée (le fichier est en écriture seule). Si l’argument `pmode` a la valeur `_S_IWRITE`, l’écriture n’est pas autorisée (le fichier est en lecture seule). Par exemple, si le bit d’écriture est défini dans le masque, les nouveaux fichiers sont en lecture seule. Notez qu’avec les systèmes d’exploitation MS-DOS et Windows, tous les fichiers sont lisibles ; il est impossible d’accorder une autorisation en écriture seule. Par conséquent, le fait définir le bit de lecture avec `_umask` n’a aucun effet sur les modes du fichier.  
  
 Si `pmode` n’est pas une combinaison de l’une des constantes manifestes ou incorpore un autre ensemble de constantes, la fonction les ignore simplement.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_umask`|\<io.h>, \<sys/stat.h>, \<sys/types.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
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
