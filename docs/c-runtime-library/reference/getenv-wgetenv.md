---
title: getenv, _wgetenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getenv
- _wgetenv
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
- _wgetenv
- getenv
- _tgetenv
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
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
ms.openlocfilehash: 2838a1c79ad97bfd665a367b2a597cb20ac70097
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv
Obtient une valeur à partir de l'environnement actuel. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `varname`  
 Nom de la variable d'environnement.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur désignant l’entrée de la table d’environnement contenant `varname`. Il est déconseillé de modifier la valeur de la variable d’environnement à l’aide du pointeur retourné. Utilisez la fonction `_putenv` pour modifier la valeur d'une variable d'environnement. La valeur de retour est `NULL` si `varname` est introuvable dans la table d’environnement.  
  
## <a name="remarks"></a>Notes  
 La fonction `getenv` recherche `varname` dans la liste des variables d'environnement. `getenv` ne respecte pas la casse dans le système d'exploitation Windows. `getenv` et `_putenv` utilisent la copie de l’environnement vers lequel la variable globale `_environ` pointe pour accéder à l’environnement. `getenv` fonctionne uniquement sur les structures de données accessibles à la bibliothèque Runtime et non sur l’environnement « segment » créé par le système d’exploitation pour le processus. Ainsi, les programmes qui utilisent l’argument `envp` pour [main](../../cpp/main-program-startup.md) ou [wmain](../../cpp/main-program-startup.md) risquent de récupérer des informations non valides.  
  
 Si `varname` a la valeur `NULL`, cette fonction appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `NULL`.  
  
 `_wgetenv` est une version à caractères larges de `getenv` ; l'argument et la valeur de retour de `_wgetenv` sont des chaînes à caractères larges. La variable globale `_wenviron` est une version à caractères larges de `_environ`.  
  
 Dans un programme MBCS (par exemple, un programme ASCII SBSC), la valeur initiale de `_wenviron` est `NULL`, car l'environnement se compose de chaînes de caractères multioctets. Ensuite, au premier appel à `_wputenv`, ou à `_wgetenv` s’il existe déjà un environnement (MBCS), un environnement à chaînes de caractères larges correspondant est créé, puis désigné par `_wenviron`.  
  
 De la même manière, dans un programme Unicode(`_wmain`), la valeur initiale de `_environ` est `NULL`, car l’environnement se compose de chaînes de caractères larges. Ensuite, au premier appel à `_putenv` ou `getenv`, s'il existe déjà un environnement (Unicode), un environnement MBCS correspondant est créé, puis désigné par `_environ`.  
  
 Quand deux copies de l'environnement (MBCS et Unicode) existent simultanément dans un programme, le système Runtime doit gérer les deux copies, ce qui entraîne des temps d'exécution plus lents. Par exemple, quand vous appelez `_putenv`, un appel à `_wputenv` est aussi exécuté automatiquement, de sorte que les deux chaînes d'environnement correspondent.  
  
> [!CAUTION]
>  Dans de rares cas, quand le système Runtime gère une version Unicode et une version multioctet de l’environnement, il se peut que ces deux versions d’environnement ne correspondent pas exactement. En effet, même si une chaîne de caractères multioctets unique est mappée à une chaîne Unicode unique, le mappage d'une chaîne Unicode unique à une chaîne de caractères multioctets n'est pas nécessairement unique. Pour plus d’informations, consultez [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Les familles de fonctions `_putenv` et `_getenv` ne sont pas thread-safe. `_getenv` peut retourner un pointeur de chaîne pendant que `_putenv` modifie la chaîne, ce qui provoque des échecs aléatoires. Assurez-vous que les appels à ces fonctions sont synchronisés.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 Pour vérifier ou modifier la valeur de la variable d’environnement `TZ`, utilisez `getenv`, `_putenv` et `_tzset`, selon les besoins. Pour plus d’informations sur `TZ`, consultez [_tzset](../../c-runtime-library/reference/tzset.md) et [_daylight, timezone et _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`getenv`|\<stdlib.h>|  
|`_wgetenv`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_getenv.c  
// compile with: /W3  
// This program uses getenv to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *libvar;  
  
   // Get the value of the LIB environment variable.  
   libvar = getenv( "LIB" ); // C4996  
   // Note: getenv is deprecated; consider using getenv_s instead  
  
   if( libvar != NULL )  
      printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects the environment  
   // variable of the current process. The command processor's  
   // environment is not changed.  
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996  
   // Note: _putenv is deprecated; consider using putenv_s instead  
  
   // Get new value.  
   libvar = getenv( "LIB" ); // C4996  
  
   if( libvar != NULL )  
      printf( "New LIB variable is: %s\n", libvar );  
}  
```  
  
```Output  
Original LIB variable is: C:\progra~1\devstu~1\vc\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [Constantes d’environnement](../../c-runtime-library/environmental-constants.md)
