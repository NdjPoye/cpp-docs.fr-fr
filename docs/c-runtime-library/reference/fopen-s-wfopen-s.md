---
title: fopen_s, _wfopen_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
dev_langs:
- C++
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
caps.latest.revision: 41
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
ms.openlocfilehash: 168d1cd797f9f7d6080f2da7aefeb8859c7f2232
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s
Ouvre un fichier. Ces versions de [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md) intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t fopen_s(   
   FILE** pFile,  
   const char *filename,  
   const char *mode   
);  
errno_t _wfopen_s(  
   FILE** pFile,  
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pFile`  
 Pointeur désignant le pointeur de fichier appelé à recevoir le pointeur vers le fichier ouvert.  
  
 [in] `filename`  
 Nom de fichier.  
  
 [in] `mode`  
 Type d'accès autorisé.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec. Pour plus d’informations sur ces codes d’erreur, consultez, [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`pFile`|`filename`|`mode`|Valeur de retour|Contenu de `pFile`|  
|-------------|----------------|------------|------------------|------------------------|  
|`NULL`|any|any|`EINVAL`|inchangé|  
|any|`NULL`|any|`EINVAL`|inchangé|  
|any|any|NULL|`EINVAL`|inchangé|  
  
## <a name="remarks"></a>Notes  
 Les fichiers ouverts par `fopen_s` et `_wfopen_s` ne peuvent pas être partagés. Si vous avez besoin de partager un fichier, utilisez [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md) avec la constante de mode de partage appropriée, par exemple, `_SH_DENYNO` pour un partage en lecture/écriture.  
  
 La fonction `fopen_s` ouvre le fichier spécifié par `filename`. `_wfopen_s` est une version à caractères larges de `fopen_s` ; les arguments de `_wfopen_s` sont des chaînes à caractères larges. Sinon, `_wfopen_s` et `fopen_s` se comportent de la même façon.  
  
 `fopen_s` accepte les chemins d'accès valides sur le système de fichiers au point d'exécution ; les chemins d'accès UNC et les chemins d'accès qui impliquent des lecteurs réseau mappés sont acceptés par `fopen_s` du moment où le système qui exécute le code a accès au partage ou au lecteur réseau mappé au moment de l'exécution. Quand il s'agit de construire des chemins d'accès pour `fopen_s`, ne faites pas d'hypothèses quant à la disponibilité des lecteurs, chemins d'accès ou partages réseau dans l'environnement d'exécution. Vous pouvez utiliser des barres obliques (/) ou des barres obliques inverses (\\) comme séparateurs de répertoire dans un chemin.  
  
 Ces fonctions valident leurs paramètres. Si `pFile`, `filename` ou `mode` est un pointeur null, ces fonctions génèrent une exception de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Vérifiez toujours la valeur de retour pour savoir si la fonction a abouti avant d'effectuer d'autres opérations sur le fichier. Si une erreur se produit, le code d'erreur est retourné et la variable globale `errno` est définie. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="unicode-support"></a>Prise en charge Unicode  
 `fopen_s` prend en charge les flux de fichiers Unicode. Pour ouvrir un fichier Unicode nouveau ou existant, passez un indicateur `ccs` qui spécifie le codage souhaité sur `fopen_s` :  
  
 `fopen_s(&fp, "newfile.txt", "rw, ccs=`*encodage*`");`  
  
 Valeurs autorisées de *codage* sont `UNICODE`, `UTF-8`, et `UTF-16LE`. Si aucune valeur n’est spécifiée il *codage*, `fopen_s` utilise le codage ANSI.  
  
 Si le fichier existe déjà et qu'il est ouvert pour lecture ou ajout, la marque d'ordre d'octet (BOM, Byte Order Mark), si elle est présente dans le fichier, détermine le codage. Le codage BOM est prioritaire sur le codage spécifié par l'indicateur `ccs`. Le codage `ccs` est utilisé uniquement quand aucune marque BOM n'est présente ou si le fichier est un nouveau fichier.  
  
> [!NOTE]
>  La détection BOM s'applique uniquement aux fichiers ouverts en mode Unicode, autrement dit, en passant l'indicateur `ccs`.  
  
 Le tableau suivant fait la synthèse des modes pour les différents indicateurs `ccs` donnés à `fopen_s` et pour les marques BOM présentes dans le fichier.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Codages utilisés selon l'indicateur ccs et la marque BOM  
  
|Indicateur`ccs` |Aucune marque BOM (ou nouveau fichier)|Marque BOM : UTF-8|Marque BOM : UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 Une marque BOM est écrite automatiquement dans les fichiers ouverts pour écriture en mode Unicode.  
  
 Si `mode` est « un, ccs =*codage*», `fopen_s` tente d’abord d’ouvrir le fichier avec accès en lecture et en écriture. En cas de réussite, la fonction lit la marque BOM pour déterminer le codage du fichier ; en cas d'échec, elle utilise le codage par défaut pour le fichier. Dans les deux cas, `fopen_s` rouvre le fichier avec un accès en écriture seule. (Cela s'applique uniquement au mode `a`, et non à `a+`.)  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen_s`|`fopen_s`|`fopen_s`|`_wfopen_s`|  
  
 La chaîne de caractères `mode` spécifie le type d'accès demandé pour le fichier, comme suit.  
  
 `"r"`  
 Ouvre pour l'accès en lecture. Si le fichier n'existe pas ou est introuvable, l'appel à `fopen_s` échoue.  
  
 `"w"`  
 Ouvre un fichier vide pour l'accès en écriture. Si le fichier existe, son contenu est détruit.  
  
 `"a"`  
 Ouvre pour un accès en écriture à la fin du fichier (ajout) sans supprimer le marqueur de fin de fichier (EOF) avant l'écriture de nouvelles données dans le fichier. Crée le fichier s'il n'existe pas.  
  
 `"r+"`  
 Ouvre pour l'accès en lecture et en écriture. (Le fichier doit exister.)  
  
 `"w+"`  
 Ouvre un fichier vide pour l'accès en lecture et en écriture. Si le fichier existe, son contenu est détruit.  
  
 `"a+"`  
 S'ouvre pour lecture et ajout. L'opération d'ajout inclut la suppression du marqueur EOF préalablement à l'écriture de nouvelles données et à la restauration du marqueur EOF à l'issue de l'écriture. Crée le fichier s'il n'existe pas.  
  
 Quand un fichier est ouvert en utilisant le type d'accès `"a"` ou `"a+"`, toutes les opérations d'écriture se produisent à la fin du fichier. Le pointeur de fichier peut être repositionné à l'aide de `fseek` ou `rewind`, mais il est toujours redéplacé à la fin du fichier avant toute opération d'écriture pour empêcher le remplacement des données existantes.  
  
 Le mode `"a"` ne supprime pas le marqueur EOF avant l'ajout des données au fichier. Après l'ajout, la commande MS-DOS TYPE affiche uniquement les données jusqu'au marqueur EOF d'origine, et non les données qui sont ajoutées au fichier. Le mode `"a+"` supprime le marqueur EOF avant l'ajout des données au fichier. Après l'ajout, la commande MS-DOS TYPE affiche toutes les données du fichier. Le mode `"a+"` est obligatoire pour ajouter des données à un fichier de flux qui se termine par le marqueur EOF Ctrl+Z.  
  
 Lorsque le `"r+"`, `"w+",` ou `"a+"` type d’accès est spécifié, la lecture et l’écriture sont autorisées. (On dit que le fichier est ouvert pour « mise à jour ».) Toutefois, lorsque vous basculez de la lecture à l'écriture, l'opération d'entrée doit rencontrer un marqueur EOF. S'il n'existe aucun marqueur EOF, vous devez faire un appel intermédiaire à une fonction de positionnement de fichier. Les fonctions de positionnement de fichier sont `fsetpos`, `fseek` et `rewind`. Quand vous passez de l'écriture à la lecture, vous devez faire un appel intermédiaire à `fflush` ou à une fonction de positionnement de fichier.  
  
 Outre les valeurs ci-dessus, les caractères suivants peuvent être inclus dans `mode` pour spécifier le mode de traduction pour les caractères de nouvelle ligne :  
  
 `t`  
 Ouvrir en mode texte (traduit). Dans ce mode, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture/écriture avec `"a+"`, `fopen_s` recherche un Ctrl+Z à la fin du fichier et le supprime, si possible. En effet, l'utilisation des fonctions `fseek` et `ftell` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `fseek` vers la fin du fichier.  
  
 En outre, en mode texte, combinaisons de sauts de ligne de chariot sont traduites en sauts de ligne uniques en entrée, et les caractères de saut de ligne sont traduits en combinaisons de sauts de ligne de chariot en sortie. Lorsqu'une fonction d'E/S de flux Unicode s'exécute en mode texte (comportement par défaut), on suppose que le flux source ou de destination est une séquence de caractères multioctets. Par conséquent, les fonctions d'entrée de flux Unicode convertissent les caractères multioctets en caractères larges (comme suite à un appel à la fonction `mbtowc` ). Pour la même raison, les fonctions de flux de sortie Unicode convertissent les caractères larges en caractères multioctets (comme suite à un appel à la fonction `wctomb` ).  
  
 `b`  
 Ouvrir en mode binaire (non traduit) ; les traductions implique la suppression des caractères de retour chariot et de saut de ligne.  
  
 Si `t` ou `b` n'est pas donné dans `mode`, le mode de traduction par défaut est défini par la variable globale [_fmode](../../c-runtime-library/fmode.md). Si `t` ou `b` a l'argument comme préfixe, la fonction échoue et retourne `NULL`.  
  
 Pour plus d’informations sur l’utilisation des modes texte et binaire dans les E/S de flux Unicode et multioctets, consultez [E/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md) et [E/S de flux Unicode en modes texte et binaire](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 Activer l'indicateur de validation pour le `filename` associé, afin que le contenu de la mémoire tampon de fichier soit écrit directement sur disque si `fflush` ou `_flushall` est appelé.  
  
 `n`  
 Réinitialiser l'indicateur de validation pour le `filename` associé à la valeur « no-commit » Il s'agit de la valeur par défaut. Substitue également l'indicateur de validation global si vous liez votre programme avec COMMODE.OBJ. La valeur par défaut de l’indicateur de validation globale est « no-commit », sauf si vous liez explicitement votre programme avec COMMODE.OBJ (consultez [Link Options](../../c-runtime-library/link-options.md)).  
  
 `N`  
 Indique que le fichier n'est pas hérité par les processus enfants.  
  
 `S`  
 Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès séquentiel à partir du disque.  
  
 `R`  
 Indique que la mise en cache est optimisée pour, mais non limitée à, l'accès aléatoire à partir du disque.  
  
 `T`  
 Spécifie un fichier comme temporaire. Si possible, il n'est pas vidé sur disque.  
  
 `D`  
 Spécifie un fichier comme temporaire. Il est supprimé lorsque le dernier pointeur de fichier est fermé.  
  
 `ccs=ENCODING`  
 Spécifie le jeu de caractères codé à utiliser (UTF-8, UTF-16LE et UNICODE) pour ce fichier. Ne spécifiez pas ce paramètre si vous voulez un codage ANSI.  
  
 Les caractères valides pour la chaîne `mode` utilisée dans `fopen_s` et `_fdopen` correspondent aux arguments `oflag` utilisés dans [_open](../../c-runtime-library/reference/open-wopen.md) et [_sopen](../../c-runtime-library/reference/sopen-wsopen.md), comme suit.  
  
|Caractères en mode chaîne|Valeur `oflag` équivalente pour `_open`/`_sopen`|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND`(généralement `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (généralement `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY`(généralement `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR`(généralement `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Aucun|  
|`n`|Aucun|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Si vous utilisez le mode `rb`, vous n'aurez pas besoin de porter votre code, et attendez-vous à lire une majeure partie du fichier et/ou ne vous souciez pas des performances réseau ; des fichiers Win32 mappés en mémoire peuvent aussi être une option.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fopen_s`|\<stdio.h>|  
|`_wfopen_s`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
 Les options de `mode` `c`, `n` et `t` sont des extensions Microsoft pour `fopen_s` et `_fdopen` et ne doivent pas être utilisées là où la portabilité ANSI est souhaitée.  
  
## <a name="example"></a>Exemple  
  
```C  
// crt_fopen_s.c  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   errno_t err;  
  
   // Open for read (will fail if file "crt_fopen_s.c" does not exist)  
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );  
   if( err == 0 )  
   {  
      printf( "The file 'crt_fopen_s.c' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'crt_fopen_s.c' was not opened\n" );  
   }  
  
   // Open for write   
   err = fopen_s( &stream2, "data2", "w+" );  
   if( err == 0 )  
   {  
      printf( "The file 'data2' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'data2' was not opened\n" );  
   }  
  
   // Close stream if it is not NULL   
   if( stream )  
   {  
      err = fclose( stream );  
      if ( err == 0 )  
      {  
         printf( "The file 'crt_fopen_s.c' was closed\n" );  
      }  
      else  
      {  
         printf( "The file 'crt_fopen_s.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:  
   int numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen_s.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
