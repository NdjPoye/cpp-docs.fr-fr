---
title: "getenv, _wgetenv | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv"
  - "_wgetenv"
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
  - "_wgetenv"
  - "getenv"
  - "_tgetenv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tgetenv (fonction)"
  - "_wgetenv (fonction)"
  - "valeurs d'environnement"
  - "variables d'environnement"
  - "getenv (fonction)"
  - "tgetenv (fonction)"
  - "wgetenv (fonction)"
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getenv, _wgetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une valeur de l'environnement actuel.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### Paramètres  
 `varname`  
 Nom de la variable d'environnement  
  
## Valeur de retour  
 Retourne un pointeur vers l'entrée de table d'environnement contenant `varname`.  Il est déconseillé de modifier la variable d'environnement à l'aide du pointeur retourné.  Utilisez la fonction `_putenv` pour modifier la valeur d'une variable d'environnement.  La valeur de retour est `NULL` si `varname` est introuvable dans la table d'environnement.  
  
## Notes  
 La fonction `getenv` recherche `varname` dans la liste des variables d'environnement.  `getenv` ne respecte pas la casse dans le système d'exploitation Windows.  `getenv` et `_putenv` utilisent la copie de l'environnement auquel la variable globale `_environ` pointe pour accéder à l'environnement.  `getenv` fonctionne uniquement sur les structures de données accessibles à la bibliothèque Runtime et non sur le "segment d'environnement créé pour le processus par le système d'exploitation.  Par conséquent, les programmes qui utilisent l'argument `envp` pour [main](../../cpp/main-program-startup.md) ou [wmain](../../cpp/main-program-startup.md) peuvent récupérer des informations non valides.  
  
 Si `varname` a la valeur `NULL`, cette fonction appelle un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `NULL`.  
  
 `_wgetenv` est une version caractères larges de `getenv`; l'argument et la valeur de retour de  `_wgetenv` sont des chaînes de caractères larges.  La variable globale `_wenviron` est une version à caractère élargi de `_environ`.  
  
 Dans un programme MBCS \(par exemple, dans un programme ASCII SBCS\), `_wenviron` est initialement `NULL` parce que l'environnement est composé des chaînes de caractères multioctets.  Ensuite, au premier appel de `_wputenv`, ou de `_wgetenv` si un environnement \(MBCS\) existe déjà, un environnement de chaîne à caractère élargi correspondant est créé, et `_wenviron` pointe vers lui.  
  
 De même dans un programme Unicode \(`_wmain`\), `_environ` est initialement `NULL` parce que l'environnement est composé des chaînes à caractère élargi.  Ensuite, au premier appel de `_putenv`, ou de `getenv` si un environnement \(Unicode\) existe déjà, un environnement MBCS correspondant est créé, et `_environ` pointe vers lui.  
  
 Lorsque deux copies de l'environnement \(MBCS et Unicode\) existent simultanément dans un programme, le système runtime doit conserver les deux copies, ce qui entraînerait une durée d'exécution plus lente.  Par exemple, lorsque vous appelez `_putenv`, un appel à `_wputenv` est exécuté automatiquement, afin que les deux chaînes d'environnement correspondent.  
  
> [!CAUTION]
>  Dans quelques cas rares, lorsque le système runtime conserve une version Unicode et une version multioctets de l'environnement, ces versions de deux environnements peuvent ne pas correspondre exactement.  En effet, bien qu'aucune unique carte de chaînes multioctets à une seule chaîne Unicode, le mappage d'une seule chaîne Unicode en une chaîne de caractères multioctets n'est pas nécessairement unique.  Pour plus d'informations, consultez [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Les familles de fonctions `_putenv` et `_getenv` ne sont pas sécurisées du point de vue du thread.  `_getenv` peut retourner un pointeur de chaîne alors que `_putenv` modifie la chaîne, provoquant des défaillances aléatoires.  Assurez\-vous que les appels à ces fonctions sont synchronisés.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 Pour vérifier ou modifier la valeur de la variable d'environnement `TZ`, utilisez `getenv`, l'`_putenv` et l'`_tzset` selon les besoins.  Pour plus d'informations sur `TZ`, consultez [\_tzset](../../c-runtime-library/reference/tzset.md) et [\_daylight, fuseau horaire, et \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`getenv`|\<stdlib.h\>|  
|`_wgetenv`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **La variable d'origine LIB est : C:\\progra ~1\\devstu~1\\vc\\lib**  
**La nouvelle variable LIB est : c:\\mylib ; c:\\yourlib**   
## Équivalent .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [Constantes d'environnement](../../c-runtime-library/environmental-constants.md)