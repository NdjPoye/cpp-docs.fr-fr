---
title: "_putenv_s, _wputenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wputenv_s"
  - "_putenv_s"
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
  - "putenv_s"
  - "wputenv_s"
  - "_wputenv_s"
  - "_putenv_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putenv_s (fonction)"
  - "_wputenv_s (fonction)"
  - "variables d'environnement, créer"
  - "variables d'environnement, supprimer"
  - "variables d'environnement, modifier"
  - "putenv_s (fonction)"
  - "wputenv_s (fonction)"
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _putenv_s, _wputenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée, modifie ou supprime des variables d'environnement.  Il s'agit de versions de [\_putenv, \_wputenv](../../c-runtime-library/reference/putenv-wputenv.md), mais qui intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW \(éventuellement en anglais\)](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _putenv_s(  
   const char *name,  
   const char *value   
);  
errno_t _wputenv_s(  
   const wchar_t *name,  
   const wchar_t *value  
);  
```  
  
#### Paramètres  
 `name`  
 Nom de la variable d'environnement.  
  
 `value`  
 Valeur à attribuer à la variable d'environnement.  
  
## Valeur de retour  
 Retourne 0 en cas de réussite et un code d'erreur dans le cas contraire.  
  
### Conditions d'erreur  
  
|`name`|`value`|Valeur de retour|  
|------------|-------------|----------------------|  
|`NULL`|tous|`EINVAL`|  
|tous|`NULL`|`EINVAL`|  
  
 Si l'une des conditions d'erreur se produit, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EINVAL` et définissent `errno` avec la valeur `EINVAL`.  
  
## Notes  
 La fonction `_putenv_s` ajoute de nouvelles variables d'environnement ou modifie les valeurs des variables d'environnement existantes.  Les variables d'environnement définissent l'environnement d'exécution d'un processus \(par exemple, le chemin de recherche par défaut pour les bibliothèques à lier à un programme\).  `_wputenv_s` est une version à caractères larges de `_putenv_s` ; l'argument `envstring` de `_wputenv_s` est une chaîne à caractères larges.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tputenv_s`|`_putenv_s`|`_putenv_s`|`_wputenv_s`|  
  
 `name` est le nom de la variable d'environnement à ajouter ou modifier et `value` est la valeur de la variable.  Si `name` fait déjà partie de l'environnement, sa valeur est remplacée par `value` ; sinon, la nouvelle variable `name` et sa valeur `value` sont ajoutées à l'environnement.  Vous pouvez supprimer une variable de l'environnement en spécifiant une chaîne vide \(c'est\-à\-dire, ""\) pour `value`.  
  
 `_putenv_s` et `_wputenv_s` affectent uniquement l'environnement local au processus actif ; vous ne pouvez pas les utiliser pour modifier l'environnement au niveau de la commande.  Ces fonctions agissent uniquement sur les structures de données accessibles à la bibliothèque Runtime et non sur l'environnement « segment » que le système d'exploitation crée pour un processus.  Quand le processus actif se termine, l'environnement repasse au niveau du processus appelant qui, dans la plupart des cas, est le niveau du système d'exploitation.  Cependant, l'environnement modifié peut être passé aux nouveaux processus créés par `_spawn`, `_exec` ou `system`, et ces nouveaux processus obtiennent les nouveaux éléments ajoutés par `_putenv_s` et `_wputenv_s`.  
  
 Ne modifiez pas directement une entrée d'environnement ; utilisez plutôt `_putenv_s` ou `_wputenv_s`.  En effet, le fait de libérer directement des éléments du tableau global `_environ[]` pourrait provoquer l'adressage d'une mémoire non valide.  
  
 `getenv` et `_putenv_s` utilisent la variable globale `_environ` pour accéder à la table d'environnement ; `_wgetenv` et `_wputenv_s` utilisent `_wenviron`.  `_putenv_s` et `_wputenv_s` peuvent modifier la valeur de `_environ` et `_wenviron`, et ainsi invalider l'argument `envp` de `main` et l'argument `_wenvp` de `wmain`.  Par conséquent, il est plus sûr d'utiliser `_environ` ou `_wenviron` pour accéder aux informations d'environnement.  Pour plus d'informations sur la relation de `_putenv_s` et `_wputenv_s` vis\-à\-vis des variables globales, consultez [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Les familles de fonctions `_putenv_s` et `_getenv_s` ne sont pas thread\-safe.  `_getenv_s` peut retourner un pointeur de chaîne pendant que `_putenv_s` modifie la chaîne, ce qui provoque par voie de conséquence des échecs aléatoires.  Assurez\-vous que les appels à ces fonctions sont synchronisés.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_putenv_s`|\<stdlib.h\>|  
|`_wputenv_s`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Pour obtenir un exemple qui montre comment utiliser `_putenv_s`, consultez [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)