---
title: "_searchenv, _wsearchenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_searchenv"
  - "_wsearchenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsearchenv"
  - "_tsearchenv"
  - "wsearchenv"
  - "_searchenv"
  - "searchenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_searchenv (fonction)"
  - "_tsearchenv (fonction)"
  - "_wsearchenv (fonction)"
  - "chemins d'accès d'environnement"
  - "chemins d'accès d'environnement, rechercher des fichiers"
  - "fichiers (C++), rechercher"
  - "searchenv (fonction)"
  - "tsearchenv (fonction)"
  - "wsearchenv (fonction)"
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# _searchenv, _wsearchenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilise des chemins d'accès d'environnement pour rechercher un fichier.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_searchenv\_s, \_wsearchenv\_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char *pathname   
);  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname   
);  
template <size_t size>  
void _searchenv(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
void _wsearchenv(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### Paramètres  
 `filename`  
 Nom du fichier à rechercher.  
  
 `varname`  
 Environnement dans lequel effectuer la recherche.  
  
 `pathname`  
 Mémoire tampon destinée à stocker le chemin d'accès complet.  
  
## Notes  
 La routine `_searchenv` recherche le fichier cible dans le domaine spécifié.  La variable `varname` peut être un environnement ou une variable définie par l'utilisateur quelconque, par exemple, `PATH`, `LIB` ou `INCLUDE`, qui spécifie une liste de chemins d'accès de répertoires.  Sachant que `_searchenv` respecte la casse, `varname` doit correspondre à la casse de la variable d'environnement.  
  
 La routine recherche d'abord le fichier dans le répertoire de travail actuel.  Si elle ne le trouve pas, elle parcourt les répertoires spécifiés par la variable d'environnement.  Si le fichier cible se trouve dans l'un de ces répertoires, le chemin d'accès qui vient d'être créé est copié dans `pathname`.  Si le fichier `filename` est introuvable, `pathname` contient une chaîne vide se terminant par null.  
  
 La mémoire tampon `pathname` doit faire une longueur minimale de `_MAX_PATH` caractères pour loger le nom de chemin d'accès construit dans son intégralité.  Sinon, `_searchenv` risque de saturer la mémoire tampon `pathname` et occasionner un comportement inattendu.  
  
 `_wsearchenv` est une version à caractères larges de `_searchenv`, et les arguments de `_wsearchenv` sont des chaînes à caractères larges.  Sinon, `_wsearchenv` et `_searchenv` se comportent de la même façon.  
  
 Si `filename` est une chaîne vide, ces fonctions retournent `ENOENT`.  
  
 Si `filename` ou `pathname` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
 Pour plus d'informations sur `errno` et les codes d'erreurs, consultez [errno, constantes](../../c-runtime-library/errno-constants.md).  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et plus sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tsearchenv`|`_searchenv`|`_searchenv`|`_wsearchenv`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_searchenv`|\<stdlib.h\>|  
|`_wsearchenv`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_searchenv.c  
// compile with: /W3  
// This program searches for a file in  
// a directory that's specified by an environment variable.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
  
   // Search for file in PATH environment variable:  
   _searchenv( searchfile, envvar, pathbuffer ); // C4996  
   // Note: _searchenv is deprecated; consider using _searchenv_s  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **Path for CL.EXE:**  
**C:\\Program Files\\Microsoft Visual Studio 8\\VC\\BIN\\CL.EXE**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [\_searchenv\_s, \_wsearchenv\_s](../../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)