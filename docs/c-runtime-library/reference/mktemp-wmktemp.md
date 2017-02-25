---
title: "_mktemp, _wmktemp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmktemp"
  - "_mktemp"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tmktemp"
  - "wmktemp"
  - "tmktemp"
  - "_wmktemp"
  - "_mktemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktemp (fonction)"
  - "_tmktemp (fonction)"
  - "_wmktemp (fonction)"
  - "fichiers (C++), temporaires"
  - "mktemp (fonction)"
  - "fichiers temporaires (C++)"
  - "tmktemp (fonction)"
  - "wmktemp (fonction)"
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _mktemp, _wmktemp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nom de fichier unique.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_mktemp\_s, \_wmktemp\_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## Syntaxe  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### Paramètres  
 `template`  
 Motif de nom de fichier.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers le fichier ouvert.  La fonction retourne `NULL` si `template` est mal formé ou plusieurs noms uniques ne peuvent être créés à partir de le modèle donné.  
  
## Notes  
 La fonction d'`_mktemp` crée un seul nom de fichier en modifiant l'argument `template`.  `_mktemp` gère automatiquement des arguments de chaîne de caractères multi\-octets appropriés en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation par le système runtime.  `_wmktemp` est une version caractères larges de `_mktemp`; l'argument et la valeur de retour de  `_wmktemp` sont des chaînes de caractères larges.  `_wmktemp` et `_mktemp` se comportent de la même manière, sauf que `_wmktemp` ne gère pas les chaînes de caractères multi\-octets.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 L'argument `template` a la forme `base`XXXXXX, où `base` est la partie du nouveau nom de fichier que vous spécifiez et chaque X est un espace réservé pour un caractère fourni par `_mktemp`.  Chaque caractère d'espace réservé dans `template` doit être un X majuscule.  `_mktemp` conserve `base` et remplace le premier X de fin par une lettre de l'alphabet.  `_mktemp` remplace les X de fin suivants par une valeur à cinq chiffres ; cette valeur est un nombre unique qui identifie le processus appelant, ou dans les applications multithread, le thread appelant.  
  
 Chaque appel réussi à  `_mktemp` modifie `template`.  Dans chaque appel suivant du même processus ou thread avec le même argument `template`, `_mktemp` recherche des noms de fichier qui correspondent aux noms retournés par `_mktemp` dans les appels précédents.  Si aucun fichier n'existe pour le nom spécifié, `_mktemp` retourne ce nom.  Si des fichiers existent pour tous les noms précédemment retournés, `_mktemp` crée un nouveau nom en remplaçant la lettre qu'il a utilisée dans le nom précédemment retourné par la lettre minuscule suivante disponible, dans l'ordre, de « a » à « z ».  Par exemple, si : `base` est:  
  
```  
fn  
```  
  
 et la valeur à cinq chiffres fournie par `_mktemp` est 12345, le prénom retourné est :  
  
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
  
 `_mktemp` peut créer un maximum de 26 noms de fichier uniques pour toute combinaison donnée des valeurs de base et du modèle.  Par conséquent, FNZ12345 est le dernier nom de fichier unique que `_mktemp` peut créer pour `base` et les valeurs`template` utilisées dans cet exemple.  
  
 En cas de échec, `errno` est défini.  Si `template` a un format non valide \(par exemple, moins de 6 x\), `errno` a la valeur `EINVAL`.  Si `_mktemp` impossible de créer un nom unique car les noms de fichiers 26 possibles existe déjà, `_mktemp` définit le modèle avec une chaîne vide et retourne `EEXIST`.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mktemp`|\<io.h,\>|  
|`_wmktemp`|\<io.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
  **Un seul nom de fichier est fna03912**  
**Un seul nom de fichier est fnb03912**  
**Un seul nom de fichier est fnc03912**  
**Un seul nom de fichier est fnd03912**  
**Un seul nom de fichier est fne03912**  
**Un seul nom de fichier est fnf03912**  
**Un seul nom de fichier est fng03912**  
**Un seul nom de fichier est fnh03912**  
**Un seul nom de fichier est fni03912**  
**Un seul nom de fichier est fnj03912**  
**Un seul nom de fichier est fnk03912**  
**Un seul nom de fichier est fnl03912**  
**Un seul nom de fichier est fnm03912**  
**Un seul nom de fichier est fnn03912**  
**Un seul nom de fichier est fno03912**  
**Un seul nom de fichier est fnp03912**  
**Un seul nom de fichier est fnq03912**  
**Un seul nom de fichier est fnr03912**  
**Un seul nom de fichier est fns03912**  
**Un seul nom de fichier est fnt03912**  
**Un seul nom de fichier est fnu03912**  
**Un seul nom de fichier est fnv03912**  
**Un seul nom de fichier est fnw03912**  
**Un seul nom de fichier est fnx03912**  
**Un seul nom de fichier est fny03912**  
**Un seul nom de fichier est fnz03912**  
**Problème de création de la classe de modèle**  
**Extraire les noms de fichiers.**   
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
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)