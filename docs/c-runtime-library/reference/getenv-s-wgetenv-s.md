---
title: getenv_s, _wgetenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getenv_s
- _wgetenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
dev_langs:
- C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 42
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 77720b4c6057913f8167dc0ceb9a6ac398c7c1c2
ms.lasthandoff: 02/24/2017

---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s
Obtient une valeur à partir de l'environnement actuel. Ces versions de [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md) intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char* buffer,  
   size_t numberOfElements,  
   const char *varname   
);  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *varname   
);  
template <size_t size>  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char (&buffer)[size],  
   const char *varname   
); // C++ only  
template <size_t size>  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t (&buffer)[size],  
   const wchar_t *varname   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pReturnValue`  
 Taille de mémoire tampon nécessaire ou 0 si la variable est introuvable.  
  
 `buffer`  
 Mémoire tampon chargée de stocker la valeur de la variable d'environnement.  
  
 `numberOfElements`  
 Taille de la `buffer`.  
  
 `varname`  
 Nom de la variable d'environnement.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite ; code d'erreur en cas d'échec.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|Valeur de retour|  
|--------------------|--------------|------------------------|---------------|------------------|  
|`NULL`|any|any|any|`EINVAL`|  
|any|`NULL`|>0|any|`EINVAL`|  
|any|any|any|`NULL`|`EINVAL`|  
  
 Ces conditions d’erreur appellent un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, les fonctions affectent à `errno` la valeur `EINVAL` et retournent `EINVAL`.  
  
 De même, si la mémoire tampon est trop petite, ces fonctions retournent `ERANGE`. Elles n'appellent pas de gestionnaire de paramètres non valides. Elles écrivent la taille de mémoire tampon nécessaire dans `pReturnValue` et permettent ainsi aux programmes de rappeler la fonction avec une mémoire tampon plus grande.  
  
## <a name="remarks"></a>Notes  
 La fonction `getenv_s` recherche `varname` dans la liste des variables d'environnement. `getenv_s` ne respecte pas la casse dans le système d'exploitation Windows. `getenv_s` et `_putenv_s` utilisent la copie de l'environnement vers laquelle pointe la variable globale `_environ` pour accéder à l'environnement. `getenv_s` fonctionne uniquement sur les structures de données accessibles à la bibliothèque Runtime et non sur l'environnement « segment » que crée le système d'exploitation pour le processus. Ainsi, les programmes qui utilisent l’argument `envp` pour [main](../../cpp/main-program-startup.md) ou [wmain](../../cpp/main-program-startup.md) risquent de récupérer des informations non valides.  
  
 `_wgetenv_s` est une version à caractères larges de `getenv_s` ; l'argument et la valeur de retour de `_wgetenv_s` sont des chaînes à caractères larges. La variable globale `_wenviron` est une version à caractères larges de `_environ`.  
  
 Dans un programme MBCS (par exemple, un programme ASCII SBSC), la valeur initiale de `_wenviron` est `NULL`, car l'environnement se compose de chaînes de caractères multioctets. Ensuite, au premier appel à `_wputenv` ou `_wgetenv_s`, s'il existe déjà un environnement (MBCS), un environnement à chaînes de caractères larges correspondant est créé, puis désigné par `_wenviron`.  
  
 De la même manière, dans un programme Unicode `(_wmain`), la valeur initiale de `_environ` est `NULL`, car l'environnement se compose de chaînes de caractères larges. Ensuite, au premier appel à `_putenv` ou `getenv_s`, s'il existe déjà un environnement (Unicode), un environnement MBCS correspondant est créé, puis désigné par `_environ`.  
  
 Quand il existe simultanément deux copies de l'environnement (MBCS et Unicode) dans un programme, le système Runtime doit gérer les deux copies, ce qui ralentit les temps d'exécution. Par exemple, quand vous appelez `_putenv`, un appel à `_wputenv` est aussi exécutée automatiquement, de sorte que les deux chaînes d'environnement correspondent.  
  
> [!CAUTION]
>  Dans de rares cas, quand le système Runtime gère une version Unicode et une version multioctet de l'environnement, il se peut que les deux versions d'environnement ne correspondent pas exactement. En effet, même si une chaîne de caractères multioctets unique est mappée à une chaîne Unicode unique, le mappage d'une chaîne Unicode unique à une chaîne de caractères multioctets n'est pas nécessairement unique. Pour plus d’informations, consultez [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Les familles de fonctions `_putenv_s` et `_getenv_s` ne sont pas thread-safe. `_getenv_s` peut retourner un pointeur de chaîne pendant que `_putenv_s` modifie la chaîne, ce qui provoque par voie de conséquence des échecs aléatoires. Assurez-vous que les appels à ces fonctions sont synchronisés.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite ainsi d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 Pour vérifier ou modifier la valeur de la variable d'environnement `TZ`, utilisez `getenv_s`, `_putenv` et `_tzset`, selon les besoins. Pour plus d’informations sur `TZ`, consultez [_tzset](../../c-runtime-library/reference/tzset.md) et [_daylight, _dstbias, _timezone et _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`getenv_s`|\<stdlib.h>|  
|`_wgetenv_s`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
  
      // crt_getenv_s.c  
// This program uses getenv_s to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* libvar;  
   size_t requiredSize;  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
   if (requiredSize == 0)  
   {  
      printf("LIB doesn't exist!\n");  
      exit(1);  
   }  
  
   libvar = (char*) malloc(requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the value of the LIB environment variable.  
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects  
   // the environment variable of the current process. The command  
   // processor's environment is not changed.  
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
  
   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the new value of the LIB environment variable.   
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "New LIB variable is: %s\n", libvar );  
  
   free(libvar);  
}  
```  
  
```Output  
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [Constantes d’environnement](../../c-runtime-library/environmental-constants.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_dupenv_s, _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)
