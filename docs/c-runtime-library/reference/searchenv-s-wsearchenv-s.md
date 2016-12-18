---
title: "_searchenv_s, _wsearchenv_s | Microsoft Docs"
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
  - "_wsearchenv_s"
  - "_searchenv_s"
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
  - "_searchenv_s"
  - "_wsearchenv_s"
  - "wsearchenv_s"
  - "searchenv_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_searchenv_s (fonction)"
  - "_tsearchenv_s (fonction)"
  - "_wsearchenv_s (fonction)"
  - "dépassements de mémoire tampon"
  - "mémoires tampons (C++), éviter les dépassements"
  - "mémoires tampons (C++), dépassements de mémoire tampon"
  - "chemins d'accès d'environnement"
  - "chemins d'accès d'environnement, rechercher des fichiers"
  - "fichiers (C++), rechercher"
  - "searchenv_s (fonction)"
  - "tsearchenv_s (fonction)"
  - "wsearchenv_s (fonction)"
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _searchenv_s, _wsearchenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche un fichier en utilisant les chemins d'environnement.  Ces versions de [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### Paramètres  
 \[in\] `filename`  
 Nom du fichier à rechercher.  
  
 \[in\] `varname`  
 Environnement dans lequel chercher.  
  
 \[out\] `pathname`  
 Mémoire tampon pour stocker le chemin d'accès complet.  
  
 \[in\] `numberOfElements`  
 Taille de la mémoire tampon pour `pathname`.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
 Si `filename` est une chaîne de caractères vide, la valeur de retour est `ENOENT`.  
  
### Conditions d'erreur  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|Valeur de retour|Contenu de `pathname`.|  
|----------------|---------------|----------------|------------------------|----------------------|----------------------------|  
|any|any|`NULL`|any|`EINVAL`|N\/A|  
|`NULL`|any|any|any|`EINVAL`|non modifié|  
|any|any|any|\<\= 0|`EINVAL`|non modifié|  
  
 Si l'une de ces conditions d'erreur se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `EINVAL`.  
  
## Notes  
 La routine `_searchenv_s` recherche le fichier cible dans le domaine spécifié.  La variable `varname` peut être tout environnement ou variable définie par l'utilisateur qui spécifie une liste de chemins d'accès aux répertoires, tels que `PATH`, `LIB`, et `INCLUDE`.  Comme `_searchenv_s` respecte la casse, `varname` doit correspondre à la casse de la variable d'environnement.  Si `varname` ne correspond pas au nom d'une variable d'environnement définie dans l'environnement du processus, la fonction retourne zéro et la variable `pathname` reste inchangée.  
  
 La routine recherche d'abord le fichier dans le répertoire de travail actuel.  Si elle ne trouve pas le fichier, elle parcourt ensuite les répertoires spécifiés par la variable d'environnement.  Si le fichier cible est dans un de ces répertoires, le chemin d'accès nouvellement créé est copié dans `pathname`.  Si le fichier `filename` est introuvable, `pathname` contient une chaîne vide terminée par le caractère NULL.  
  
 La mémoire tampon `pathname` doit être longue d'au moins `_MAX_PATH` caractères afin de pouvoir contenir le chemin d'accès construit en entier.  Sinon, `_searchenv_s` pourrait provoquer un dépassement de mémoire tampon de`pathname` ce qui occasionnerait un comportement imprévisible.  
  
 `_wsearchenv_s` est une version à caractères larges de `_searchenv_s` ; les arguments vers `_wsearchenv_s` sont des chaînes à caractères larges.  `_wsearchenv_s` et `_searchenv_s` se comportent sinon de manière identique.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h\>|  
|`_wsearchenv_s`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
  **Chemin d'accès pour CL.EXE :**  
**C:\\Program Files\\Microsoft Visual Studio 2010\\VC\\BIN\\CL.EXE**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)