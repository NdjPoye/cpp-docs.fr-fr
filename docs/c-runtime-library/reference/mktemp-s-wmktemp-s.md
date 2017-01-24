---
title: "_mktemp_s, _wmktemp_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mktemp_s"
  - "_wmktemp_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wmktemp_s"
  - "mktemp_s"
  - "_mktemp_s"
  - "_wmktemp_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktemp_s (fonction)"
  - "_tmktemp_s (fonction)"
  - "_wmktemp_s (fonction)"
  - "fichiers (C++), temporaires"
  - "mktemp_s (fonction)"
  - "fichiers temporaires (C++)"
  - "tmktemp_s (fonction)"
  - "wmktemp_s (fonction)"
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mktemp_s, _wmktemp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nom de fichier unique.  Il s'agit de versions de [\_mktemp, \_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `template`  
 Motif de nom de fichier.  
  
 `sizeInChars`  
 Taille de la mémoire tampon en caractères codés sur un octet dans `_mktemp_s`; caractères larges dans `_wmktemp_s`, notamment la marque de fin null.  
  
## Valeur de retour  
 Ces deux fonctions retournent zéro en cas de réussite ; un code d'erreur en cas d'échec.  
  
### Conditions d'erreur  
  
|`template`|`sizeInChars`|**valeur de retour**|**nouvelle valeur du modèle**|  
|----------------|-------------------|--------------------------|-----------------------------------|  
|`NULL`|any|`EINVAL`|`NULL`|  
|Format incorrect \(voir la section `Remarks` pour un format correct\)|any|`EINVAL`|Chaîne vide|  
|any|\<\= nombre de X|`EINVAL`|Chaîne vide|  
  
 Si l'une de ces conditions d'erreur ci\-dessus se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à la valeur `EINVAL` et ces fonctions retournent `EINVAL`.  
  
## Notes  
 La fonction `_mktemp_s` crée un seul nom de fichier en modifiant l'argument `template`, afin qu'après l'appel, le pointeur `template` pointe vers une chaîne qui contient le nouveau nom de fichier.  `_mktemp_s` gère automatiquement des arguments de chaîne de caractères multi\-octets appropriés en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation par le système runtime.  `_wmktemp_s` est une version à caractères larges de `_mktemp_s` ; l'argument de `_wmktemp_s` est une chaîne à caractères larges.  `_wmktemp_s` et `_mktemp_s` se comportent de la même manière, sauf que `_wmktemp_s` ne gère pas les chaînes de caractères multi\-octets.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 L'argument `template` a la forme `baseXXXXXX`, où `base` est la partie du nouveau nom de fichier que vous spécifiez et chaque X est un espace réservé pour un caractère fourni par `_mktemp_s`.  Chaque caractère d'espace réservé dans `template` doit être un X majuscule.  `_mktemp_s` conserve `base` et remplace le premier X de fin par une lettre de l'alphabet.  `_mktemp_s` remplace les X de fin suivants par une valeur à cinq chiffres ; cette valeur est un nombre unique qui identifie le processus appelant, ou dans les applications multithread, le thread appelant.  
  
 Chaque appel réussi à `_mktemp_s` modifie `template`.  Dans chaque appel suivant du même processus ou thread avec le même argument `template`, `_mktemp_s` recherche des noms de fichier qui correspondent aux noms retournés par `_mktemp_s` dans les appels précédents.  Si aucun fichier n'existe pour le nom spécifié, `_mktemp_s` retourne ce nom.  Si des fichiers existent pour tous les noms précédemment retournés, `_mktemp_s` crée un nouveau nom en remplaçant la lettre qu'il a utilisée dans le nom précédemment retourné par la lettre minuscule suivante disponible, dans l'ordre, de « a » à « z ».  Par exemple, si : `base` est:  
  
```  
fn  
```  
  
 et la valeur à cinq chiffres fournie par `_mktemp_s` est 12345, le prénom retourné est :  
  
```  
fna12345  
```  
  
 Si ce nom est utilisé pour créer le fichier FNA12345 et ce fichier existe toujours, le nom suivant retourné sur un appel du même processus ou thread avec le même `base` pour `template` est :  
  
```  
fnb12345  
```  
  
 Si FNA12345 n'existe pas, le nom suivant retourné est de nouveau:  
  
```  
fna12345  
```  
  
 `_mktemp_s` peut créer un maximum de 26 noms de fichier uniques pour toute combinaison donnée des valeurs de base et du modèle.  Par conséquent, FNZ12345 est le dernier nom de fichier unique que `_mktemp_s` peut créer pour `base` et les valeurs `template` utilisées dans cet exemple.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h,\>|  
|`_wmktemp_s`|\<io.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
## Résultat de l'exemple  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../../c-runtime-library/reference/getpid.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)