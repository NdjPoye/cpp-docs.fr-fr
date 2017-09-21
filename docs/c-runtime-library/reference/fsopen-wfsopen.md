---
title: _fsopen, _wfsopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfsopen
- _fsopen
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 20
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
ms.openlocfilehash: c53bdd4bdd5d6707e6da15def20b6375dcf6e0dd
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen
Ouvre un flux avec le partage de fichiers.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
FILE *_fsopen(   
   const char *filename,  
   const char *mode,  
   int shflag   
);  
FILE *_wfsopen(   
   const wchar_t *filename,  
   const wchar_t *mode,  
   int shflag   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `filename`  
 Nom du fichier à ouvrir.  
  
 `mode`  
 Type d'accès autorisé.  
  
 `shflag`  
 Type de partage autorisé.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers le flux. Une valeur de pointeur null indique une erreur. Si `filename` ou `mode` a la valeur `NULL` ou est une chaîne vide, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `NULL` et définissent `errno` avec la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes d’erreur et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_fsopen` ouvre le fichier spécifié par `filename` en tant que flux et prépare le fichier à la lecture ou l'écriture partagée ultérieure, tel que défini par le mode et les arguments `shflag`. `_wfsopen` est une version à caractères larges de `_fsopen` ; les arguments `filename` et `mode` de `_wfsopen` sont des chaînes à caractères larges. Sinon, `_wfsopen` et `_fsopen` se comportent de la même façon.  
  
 La chaîne de caractères `mode` spécifie le type d'accès demandé pour le fichier, comme indiqué dans le tableau suivant.  
  
|Terme|Définition|  
|----------|----------------|  
|`"r"`|Ouvre pour l'accès en lecture. Si le fichier n'existe pas ou est introuvable, l'appel à `_fsopen` échoue.|  
|`"w"`|Ouvre un fichier vide pour l'accès en écriture. Si le fichier spécifié existe, son contenu est détruit.|  
|`"a"`|Ouvre pour l'écriture à la fin du fichier (ajout) ; crée d'abord le fichier s'il n'existe pas.|  
|`"r+"`|Ouvre pour l'accès en lecture et en écriture. (Le fichier doit exister.)|  
|`"w+"`|Ouvre un fichier vide pour l'accès en lecture et en écriture. Si le fichier spécifié existe, son contenu est détruit.|  
|`"a+"`|Ouvre pour l'écriture et l'ajout ; crée d'abord le fichier s'il n'existe pas.|  
  
 Utilisez les types `"w"` et `"w+"` avec précaution, car ils peuvent détruire les fichiers existants.  
  
 Quand un fichier est ouvert avec le type d'accès `"a"` ou `"a+"`, toutes les opérations d'écriture se produisent à la fin du fichier. Le pointeur de fichier peut être repositionné à l'aide de `fseek` ou `rewind`, mais il est toujours redéplacé à la fin du fichier avant toute opération d'écriture. Par conséquent, les données existantes ne peuvent pas être remplacées. Quand le type d'accès `"r+"`, `"w+"` ou `"a+"` est spécifié, la lecture et l'écriture sont autorisées (on dit que le fichier est ouvert pour mise à jour). Cependant, quand vous basculez entre lecture et écriture, une opération intermédiaire [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) ou [rewind](../../c-runtime-library/reference/rewind.md) doit exister. La position actuelle peut éventuellement être spécifiée pour l'opération `fsetpos` ou `fseek`. Outre les valeurs ci-dessus, l'un des caractères suivants peut être inclus dans `mode` pour spécifier le mode de traduction pour les nouvelles lignes et la gestion des fichiers.  
  
|Terme|Définition|  
|----------|----------------|  
|`t`|Ouvre un fichier en mode texte (traduit). Dans ce mode, combinaisons chariot retour-ligne (CRLF) sont traduites en flux d’une seule ligne (LF) dans l’entrée et les caractères de saut de ligne sont traduits en combinaisons retour chariot-saut de ligne en sortie. De même, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture ou lecture/écriture, `_fsopen` recherche un Ctrl+Z à la fin du fichier et le supprime, si possible. En effet, l'utilisation des fonctions `fseek` et `ftell` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `fseek` vers la fin du fichier.|  
|`b`|Ouvre un fichier en mode binaire (non traduit) ; les traductions ci-dessus sont supprimées.|  
|`S`|Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès séquentiel à partir du disque.|  
|`R`|Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès aléatoire à partir du disque.|  
|`T`|Spécifie un fichier comme temporaire. Si possible, il n'est pas vidé sur disque.|  
|`D`|Spécifie un fichier comme temporaire. Il est supprimé lorsque le dernier pointeur de fichier est fermé.|  
  
 Si `t` ou `b` n'est pas spécifié dans `mode`, le mode de traduction est défini par la variable de mode par défaut `_fmode`. Si `t` ou `b` a l'argument comme préfixe, la fonction échoue et retourne `NULL`. Pour en savoir plus sur les modes texte et binaire, consultez [E/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 L'argument `shflag` est une expression constante constituée de l'une des constantes de manifeste suivantes, définies dans Share.h.  
  
|Terme|Définition|  
|----------|----------------|  
|`_SH_COMPAT`|Définit le mode de compatibilité pour les applications 16 bits.|  
|`_SH_DENYNO`|Autorise l'accès en lecture et en écriture.|  
|`_SH_DENYRD`|Refuse l'accès en lecture au fichier.|  
|`_SH_DENYRW`|Refuse l'accès en lecture et en écriture au fichier.|  
|`_SH_DENYWR`|Refuse l'accès en écriture au fichier.|  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfsopen`|`_fsopen`|`_fsopen`|`_wfsopen`|  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-têtes facultatifs|  
|--------------|---------------------|----------------------|  
|`_fsopen`|\<stdio.h>|\<share.h><br /><br /> Pour la constante de manifeste du paramètre `shflag`.|  
|`_wfsopen`|\<stdio.h> ou \<wchar.h>|\<share.h><br /><br /> Pour la constante de manifeste du paramètre `shflag`.|  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fsopen.c  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
  
   // Open output file for writing. Using _fsopen allows us to  
   // ensure that no one else writes to the file while we are  
   // writing to it.  
    //  
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )  
   {  
      fprintf( stream, "No one else in the network can write "  
                       "to this file until we are done.\n" );  
      fclose( stream );  
   }  
   // Now others can write to the file while we read it.  
   system( "type outfile" );  
}  
```  
  
```Output  
No one else in the network can write to this file until we are done.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)