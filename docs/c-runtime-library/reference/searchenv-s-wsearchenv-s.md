---
title: _searchenv_s, _wsearchenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs:
- C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
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
ms.openlocfilehash: 3b7b1d4165edb3a7e34cda665de195759784eedc
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s
Recherche un fichier en utilisant des chemins d’environnement. Ces versions de [getenv, _wgetenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 [in] `filename`  
 Nom du fichier à rechercher.  
  
 [in] `varname`  
 Environnement dans lequel effectuer la recherche.  
  
 [out] `pathname`  
 Mémoire tampon destinée à stocker le chemin d’accès complet.  
  
 [in] `numberOfElements`  
 Taille de la `pathname` mémoire tampon.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
 Si `filename` est une chaîne vide, la valeur de retour est `ENOENT`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|Valeur de retour|Contenu de `pathname`|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|any|any|`NULL`|any|`EINVAL`|N/A|  
|`NULL`|indifférent|any|indifférent|`EINVAL`|inchangé|  
|indifférent|any|any|<= 0|`EINVAL`|inchangé|  
  
 Si l’une de ces conditions d’erreur se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La routine `_searchenv_s` recherche le fichier cible dans le domaine spécifié. La variable `varname` peut être une variable d’environnement ou une variable définie par l’utilisateur quelconque qui spécifie une liste de chemins de répertoires, tels que `PATH`, `LIB` et `INCLUDE`. Sachant que `_searchenv_s` respecte la casse, `varname` doit correspondre à la casse de la variable d'environnement. Si `varname` ne correspond pas au nom d’une variable d’environnement définie dans l’environnement du processus, la fonction retourne zéro et la variable `pathname` est inchangée.  
  
 La routine recherche d’abord le fichier dans le répertoire de travail actif. Si elle ne le trouve pas, elle parcourt ensuite les répertoires spécifiés par la variable d’environnement. Si le fichier cible se trouve dans l'un de ces répertoires, le chemin d'accès qui vient d'être créé est copié dans `pathname`. Si le fichier `filename` est introuvable, `pathname` contient une chaîne vide se terminant par null.  
  
 La mémoire tampon `pathname` doit faire une longueur minimale de `_MAX_PATH` caractères pour loger le nom de chemin d'accès construit dans son intégralité. Sinon, `_searchenv_s` risque de saturer la mémoire tampon `pathname` et occasionner un comportement inattendu.  
  
 `_wsearchenv_s` est une version à caractères larges de `_searchenv_s` ; les arguments de `_wsearchenv_s` sont des chaînes à caractères larges. Sinon, `_wsearchenv_s` et `_searchenv_s` se comportent de la même façon.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h>|  
|`_wsearchenv_s`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)
