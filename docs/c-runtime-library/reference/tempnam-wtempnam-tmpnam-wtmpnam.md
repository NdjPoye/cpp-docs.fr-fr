---
title: "_tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam"
  - "_wtmpnam"
  - "tmpnam"
  - "_tempnam"
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
  - "wtempnam"
  - "_wtmpnam"
  - "wtmpnam"
  - "tmpnam"
  - "_wtempnam"
  - "_tempnam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tempnam (fonction)"
  - "_ttmpnam (fonction)"
  - "_wtempnam (fonction)"
  - "_wtmpnam (fonction)"
  - "noms de fichiers (C++), créer temporaire"
  - "noms de fichiers (C++), temporaires"
  - "tempnam (fonction)"
  - "fichiers temporaires, créer"
  - "tmpnam (fonction)"
  - "ttmpnam (fonction)"
  - "wtempnam (fonction)"
  - "wtmpnam (fonction)"
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _tempnam, _wtempnam, tmpnam, _wtmpnam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génére des noms que vous pouvez utiliser pour créer des fichiers temporaires.  Des versions plus sécurisées de certaines de ces fonctions sont disponibles ; consultez [tmpnam\_s, \_wtmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## Syntaxe  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### Paramètres  
 `prefix`  
 La chaîne qui sera ajoutée au début des noms retournés par `_tempnam`.  
  
 `dir`  
 Le chemin d'accès utilisé dans le nom du fichier s'il n'existe aucune variable d'environnement TMP, ou si TMP n'est pas un répertoire valide.  
  
 `str`  
 Pointeur qui contiendra le nom généré et qui sera identique au nom retourné par la fonction.  Il s'agit d'un moyen commode d'enregistrer le nom généré.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers le nom généré ou `NULL` en cas de échec.  L'erreur peut se produire si vous tentez plus que `TMP_MAX` \(voir STDIO.H\) appels avec `tmpnam` ou si vous utilisez `_tempnam`et qu'il y a un nom de répertoire invalide spécifié dans la variable d'environnement TMP et dans le paramètre `dir`.  
  
> [!NOTE]
>  Les pointeurs retournés par `tmpnam` et le point `_wtmpnam` aux tampons statiques internes.  [disponible](../../c-runtime-library/reference/free.md) ne doit pas être appelé pour libérer les pointeurs.  `free` doit être appelé pour les pointeurs alloués par `_tempnam` et `_wtempnam`.  
  
## Notes  
 Chacune de ces fonctions retourne le nom d'un fichier qui n'existe pas.  `tmpnam` retourne un nom unique dans le répertoire de travail actuel et `_tempnam` vous permet de générer un nom unique dans un répertoire autre que le actuel.  Notez que lorsqu'un nom de fichier est ajouté au début avec une barre oblique inverse et sans informations de chemin d'accès, par exempl comme \\fname21, cela indique que le nom est valide pour le répertoire de travail actuel.  
  
 Pour `tmpnam`, vous pouvez stocker le nom de fichier généré dans `str`.  Si `str` est `NULL`, alors `tmpnam` laisse le résultat dans un tampon interne statique.  Par conséquent tout appel à cette meme fonction par la suite détruit cette valeur  Le nom généré par `tmpnam` se compose d'un nom de fichier programme généré et, après le premier appel à `tmpnam`, d'une extension de fichier composée des numéros séquentiels en base 32 \(.1\-.vvvu, lorsque `TMP_MAX` dans STDIO.H est 32,67\).  
  
 `_tempnam` génère un nom unique de répertoire choisi selon les règles suivantes :  
  
-   Si la variable d'environnement TMP est définie et est fixée sur un nom de répertoire valide, des noms de fichier seront générés pour le répertoire spécifié par TMP.  
  
-   Si la variable d'environnement TMP n'est pas définie ou si elle est définie sur le nom d'un répertoire qui n'existe pas, `_tempnam` utilise le paramètre `dir` comme chemin d'accès pour lequel il génère des noms uniques.  
  
-   Si la variable d'environnement TMP n'est pas définie ou si elle est définie sur le nom d'un répertoire qui n'existe pas, et si `dir` est `NULL` ou est associée à un nom de dossier qui n'existe pas, `_tempnam` utilise le répertoire de travail actuel pour générer des noms uniques.  Actuellement, si le TMP et `dir` spécifient des noms de répertoires qui n'existent pas, l'appel de la fonction `_tempnam` échoue.  
  
 Le nom retourné par `_tempnam` est une concaténation de `prefix` et d'un numéro séquentiel, qui seront mixés pour créer un nom de fichier unique du répertoire spécifié.  `_tempnam` génère les noms de fichiers qui n'ont aucune extension.  `_tempnam` utilise [malloc](../../c-runtime-library/reference/malloc.md) pour allouer de l'espace pour le nom de fichier ; le programme est chargé de récupérer de l'espace lorsque vous n'en avez plus besoin.  
  
 `_tempnam` et \<languageKeyword\>tmpnam\<\/languageKeyword\> gèrent automatiquement les arguments de chaîne de caractères multi\-octets comme approprié, identifiant des séquences de caractères multioctets selon la page de codes OEM extraite du système d'exploitation.  `_wtempnam` est une version caractères larges de `_tempnam`; les arguments et la valeur de retour de  `_wtempnam` sont des chaînes de caractères larges.  `_wtempnam` et `_tempnam` se comportent de la même manière que `_wtempnam` mais ne gèrent pas les chaînes de caractères multi\-octets.  `_wtmpnam` est une version caractères larges de `tmpnam`; l'argument et la valeur de retour de  `_wtmpnam` sont des chaînes de caractères larges.  `_wtmpnam` et `tmpnam` se comportent de la même manière que `_wtmpnam` mais ne gèrent pas les chaînes de caractères multi\-octets.  
  
 Si `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont définis, `_tempnam` et `_wtempnam` sont remplacés par des appels à [\_tempnam\_dbg et \_wtempnam\_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h\>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h\> ou \<wchar.h\>|  
|`tmpnam`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
  **\\ s1gk. est sécurisé pour utiliser dans un fichier temporaire.**  
**Il est sûr d'utiliser C:\\DOCUME~1\\user\\LOCALS~1\\Temp\\2\\stq2 dans un fichier temporaire.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)