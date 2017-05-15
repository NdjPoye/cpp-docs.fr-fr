---
title: _mktemp_s, _wmktemp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktemp_s
- _wmktemp_s
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
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
ms.openlocfilehash: 6231031dd0bbc5b455e3555731f711ee7de971e7
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s
Crée un nom de fichier unique. Ces versions de [_mktemp, _wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `template`  
 Modèle de nom de fichier.  
  
 `sizeInChars`  
 Taille de la mémoire tampon en caractères codés sur un octet (`_mktemp_s`) ou en caractères larges (`_wmktemp_s`), marque de fin Null comprise.  
  
## <a name="return-value"></a>Valeur de retour  
 Ces deux fonctions retournent zéro en cas de réussite, sinon un code d’erreur.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`template`|`sizeInChars`|**Valeur de retour**|**Nouvelle valeur dans le modèle**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|any|`EINVAL`|`NULL`|  
|Format incorrect (voir la section `Remarks` pour connaître le format correct)|any|`EINVAL`|Chaîne vide|  
|any|<= nombre de X|`EINVAL`|Chaîne vide|  
  
 Si l’une des conditions d’erreur ci-dessus se produit, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` est défini sur `EINVAL` et la fonction retourne `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_mktemp_s` crée un nom de fichier unique en modifiant l’argument `template`, afin qu’après l’appel, le pointeur `template` désigne une chaîne qui contient le nouveau nom de fichier. `_mktemp_s` gère automatiquement les arguments de chaîne de caractères multioctets selon le cas, en identifiant les séquences de caractères multioctets en fonction de la page de codes multioctets en cours d'utilisation par le système d'exécution. `_wmktemp_s` est une version à caractères larges de `_mktemp_s` ; l’argument de `_wmktemp_s` est une chaîne à caractères larges. `_wmktemp_s` et `_mktemp_s` se comportent de la même manière, sauf que `_wmktemp_s` ne gère pas les chaînes de caractères multioctets.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 L’argument `template` se présente sous la forme `baseXXXXXX`, où `base` est la partie du nouveau nom de fichier que vous spécifiez et chaque X est un espace réservé pour un caractère fourni par `_mktemp_s`. Chaque caractère d’espace réservé dans `template` doit être un X majuscule. `_mktemp_s` conserve `base` et remplace le premier X de fin par un caractère alphabétique. `_mktemp_s` remplace le X de fin suivant par une valeur à cinq chiffres ; cette valeur est un nombre unique qui identifie le processus appelant, ou dans les applications multithread, le thread appelant.  
  
 Chaque appel réussi à `_mktemp_s` modifie `template`. Dans chaque appel suivant du même processus ou thread avec le même argument `template`, `_mktemp_s` recherche des noms de fichier qui correspondent aux noms retournés par `_mktemp_s` dans les appels précédents. Si aucun fichier n'existe pour le nom spécifié, `_mktemp_s` retourne ce nom. Si des fichiers existent pour tous les noms précédemment retournés, `_mktemp_s` crée un nom en remplaçant le caractère alphabétique utilisé dans le nom précédemment retourné par la lettre minuscule suivante disponible, dans l'ordre, de "a" à "z". Par exemple, si `base` est :  
  
```  
fn  
```  
  
 et la valeur à cinq chiffres fournie par `_mktemp_s` est 12345, le premier nom retourné est :  
  
```  
fna12345  
```  
  
 Si ce nom est utilisé pour créer le fichier FNA12345 et si ce fichier existe toujours, le nom suivant retourné sur un appel du même processus ou thread avec la même valeur `base` pour `template` est :  
  
```  
fnb12345  
```  
  
 Si le fichier FNA12345 n'existe pas, le nom suivant retourné est de nouveau :  
  
```  
fna12345  
```  
  
 `_mktemp_s` peut créer 26 noms de fichier uniques au maximum pour toute combinaison donnée de valeurs base et template. Par conséquent, FNZ12345 est le dernier nom de fichier unique que `_mktemp_s` peut créer pour les valeurs `base` et `template` utilisées dans cet exemple.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h>|  
|`_wmktemp_s`|\<io.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)
