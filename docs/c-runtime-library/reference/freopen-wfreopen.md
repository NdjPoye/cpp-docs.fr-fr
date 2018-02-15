---
title: freopen, _wfreopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs:
- C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49f1e2cd11606d2ebe53281a9d2f1d27533b4068
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen
Réaffecte un pointeur de fichier. Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
FILE *freopen(   
   const char *path,  
   const char *mode,  
   FILE *stream   
);  
FILE *_wfreopen(   
   const wchar_t *path,  
   const wchar_t *mode,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Chemin d’accès du nouveau fichier.  
  
 `mode`  
 Type d'accès autorisé.  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers le fichier qui vient d'être ouvert. Si une erreur se produit, le fichier d'origine est fermé et la fonction retourne une valeur de pointeur `NULL`. Si `path`, `mode` ou `stream` est un pointeur null ou si `filename` est une chaîne vide, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `NULL`.  
  
 Pour plus d’informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Il existe des versions plus sécurisées de ces fonctions ; consultez [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
 Le `freopen` fonction ferme le fichier actuellement associé `stream` et réaffecte `stream` dans le fichier spécifié par `path`. `_wfreopen` est une version à caractères larges de `_freopen` ; les arguments `path` et `mode` de `_wfreopen` sont des chaînes à caractères larges. Sinon, `_wfreopen` et `_freopen` se comportent de la même façon.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen` est généralement utilisé pour rediriger les fichiers pré-ouverts `stdin`, `stdout` et `stderr` vers les fichiers spécifiés par l'utilisateur. Le nouveau fichier associé `stream` est ouvert avec `mode`, qui est une chaîne de caractères spécifiant le type d’accès demandé pour le fichier, comme suit :  
  
 `"r"`  
 Ouvre pour l'accès en lecture. Si le fichier n'existe pas ou est introuvable, l'appel à `freopen` échoue.  
  
 `"w"`  
 Ouvre un fichier vide pour l'accès en écriture. Si le fichier spécifié existe, son contenu est détruit.  
  
 `"a"`  
 Ouvre pour un accès en écriture à la fin du fichier (ajout) sans supprimer le marqueur de fin de fichier (EOF) avant l'écriture de nouvelles données dans le fichier ; crée d'abord le fichier s'il n'existe pas.  
  
 `"r+"`  
 Ouvre pour l'accès en lecture et en écriture. (Le fichier doit exister.)  
  
 `"w+"`  
 Ouvre un fichier vide pour l'accès en lecture et en écriture. Si le fichier spécifié existe, son contenu est détruit.  
  
 `"a+"`  
 Ouvre pour l'accès en lecture et l'ajout ; l'opération d'ajout inclut la suppression du marqueur EOF préalablement à l'écriture de nouvelles données dans le fichier et à la restauration du marqueur EOF à l'issue de l'écriture ; crée d'abord le fichier s'il n'existe pas.  
  
 Utilisez les types `"w"` et `"w+"` avec précaution, car ils peuvent détruire les fichiers existants.  
  
 Quand un fichier est ouvert avec le type d'accès `"a"` ou `"a+"`, toutes les opérations d'écriture se produisent à la fin du fichier. Même si le pointeur de fichier peut être repositionné à l'aide de `fseek` ou `rewind`, il est toujours redéplacé à la fin du fichier avant toute opération d'écriture. Par conséquent, les données existantes ne peuvent pas être remplacées.  
  
 Le mode `"a"` ne supprime pas le marqueur EOF avant l'ajout des données au fichier. Après l'ajout, la commande MS-DOS TYPE affiche uniquement les données jusqu'au marqueur EOF d'origine, et non les données ajoutées au fichier. Le mode `"a+"` supprime le marqueur EOF avant l'ajout des données au fichier. Après l'ajout, la commande MS-DOS TYPE affiche toutes les données du fichier. Le mode `"a+"` est obligatoire pour ajouter des données à un fichier de flux qui se termine par le marqueur EOF Ctrl+Z.  
  
 Lorsque le type d'accès `"r+"`, `"w+"` ou `"a+"` est spécifié, la lecture et l'écriture sont autorisées (on dit que le fichier est ouvert pour « mise à jour »). Cependant, quand vous basculez entre lecture et écriture, une opération intermédiaire [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) ou [rewind](../../c-runtime-library/reference/rewind.md) doit exister. La position actuelle peut éventuellement être spécifiée pour l'opération `fsetpos` ou `fseek`. Outre les valeurs ci-dessus, l'un des caractères suivants peut être inclus dans la chaîne `mode` pour spécifier le mode de traduction pour les nouvelles lignes.  
  
 `t`  
 Ouvrir dans le texte (traduit) mode ; combinaisons de sauts de ligne (CRLF) de chariot sont traduites en caractères de saut de ligne (LF) unique d’entrée ; Les caractères de saut de ligne sont traduits en combinaisons retour chariot-saut de ligne en sortie. De même, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture ou lecture et écriture avec `"a+"`, la bibliothèque Runtime recherche un Ctrl+Z à la fin du fichier et le supprime, si possible. En effet, l'utilisation de `fseek` et `ftell` pour se déplacer dans un fichier peut amener `fseek` à se comporter de manière incorrecte vers la fin du fichier. L'option `t` est une extension Microsoft qui ne doit pas être utilisée là où la portabilité ANSI est souhaitée.  
  
 `b`  
 Ouvre en mode binaire (non traduit) ; les traductions ci-dessus sont supprimées.  
  
 Si `t` ou `b` n'est pas donné dans `mode`, le mode de traduction par défaut est défini par la variable globale [_fmode](../../c-runtime-library/fmode.md). Si `t` ou `b` a l'argument comme préfixe, la fonction échoue et retourne `NULL`.  
  
 Pour en savoir plus sur les modes texte et binaire, consultez [E/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`freopen`|\<stdio.h>|  
|`_wfreopen`|\<stdio.h> ou \<wchar.h>|  
  
 La console n’est pas pris en charge dans les applications de plateforme Windows universelle (UWP). Les descripteurs de flux standard qui sont associés à la console :`stdin`, `stdout`, et `stderr`, doivent être redirigés avant que les fonctions d’exécution C de les utiliser dans les applications UWP. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_freopen.c  
// compile with: /W3  
// This program reassigns stderr to the file  
// named FREOPEN.OUT and writes a line to that file.  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   // Reassign "stderr" to "freopen.out":   
   stream = freopen( "freopen.out", "w", stderr ); // C4996  
   // Note: freopen is deprecated; consider using freopen_s instead  
  
   if( stream == NULL )  
      fprintf( stdout, "error on freopen\n" );  
   else  
   {  
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );  
      fprintf( stream, "This will go to the file 'freopen.out'\n" );  
      fclose( stream );  
   }  
   system( "type freopen.out" );  
}  
```  
  
```Output  
successfully reassigned  
This will go to the file 'freopen.out'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)