---
title: "_putenv, _wputenv | Microsoft Docs"
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
  - "_putenv"
  - "_wputenv"
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
  - "_tputenv"
  - "_wputenv"
  - "_putenv"
  - "wputenv"
  - "tputenv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putenv (fonction)"
  - "_tputenv (fonction)"
  - "_wputenv (fonction)"
  - "variables d'environnement, créer"
  - "variables d'environnement, supprimer"
  - "variables d'environnement, modifier"
  - "putenv (fonction)"
  - "tputenv (fonction)"
  - "wputenv (fonction)"
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _putenv, _wputenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée, modifie ou supprime, les variables d'environnement.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### Paramètres  
 `envstring`  
 Définition d'une chaine environnement.  
  
## Valeur de retour  
 Retourne 0 en cas de réussite ou – 1 dans le cas d'une erreur.  
  
## Notes  
 La fonction `_putenv` ajoute de nouvelles variables d'environnement ou modifie les valeurs des variables d'environnement existantes.  Les variables d'environnement définissent l'environnement dans lequel un processus s'exécute \(par exemple, le chemin de recherche par défaut pour relier les bibliothèques à un programme\).  `_wputenv` est une version à caractères larges de `_putenv`; l'argument `envstring` vers `_wputenv` est une chaîne à caractères larges.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 L'argument `envstring` doit être un pointeur vers une chaîne de la forme `varname=string`, où `varname` est le nom de la variable d'environnement à ajouter ou modifier et `string` est la valeur de la variable.  Si `varname` est déjà partie de l'environnement, sa valeur est remplacée par `string`; sinon, la nouvelle variable `varname` et sa valeur `string` sont ajoutées à l'environnement.  Supprimez une variable de l'environnement en spécifiant un `string` vide, en d'autres termes, en spécifiant seulement `varname=`.  
  
 `_putenv` et `_wputenv` affectent uniquement l'environnement qui est local au processus actuel ; vous ne pouvez pas les utiliser pour modifier l'environnement de commande niveau.  Autrement dit, ces fonctions fonctionnent uniquement sur les structures de données accessibles à la bibliothèque Runtime et non dans le segment d'environnement créé pour un processus par le système d'exploitation.  Lorsque le processus actuel se termine, l'environnement revient au niveau du processus appelant \(dans la plupart des cas, le niveau du système d'exploitation\).  Toutefois, l'environnement modifié peut être passé à tous les nouveaux processus créés par `_spawn`, `_exec`, ou `system`, et ces nouveaux processus obtiennent tous les nouveaux éléments ajoutés par `_putenv` et `_wputenv`.  
  
 Ne modifiez pas une entrée d'environnement directement : à la place, utilisez `_putenv` ou `_wputenv` pour le modifier.  En particulier, la libération directe d'éléments du tableau global `_environ[]` pourrait mener au remplissage d'une mémoire non valide.  
  
 `getenv` et `_putenv` utilisent la variable globale `_environ` pour accéder à la table d'environnement ; `_wgetenv` et `_wputenv` utilisent `_wenviron`.  `_putenv` et `_wputenv` peuvent modifier la valeur d' `_environ` et `_wenviron`, invalidant ainsi l'argument `_envp` à `main` et l'argument`wenvp` à `wmain`.  Par conséquent, il est préférable d'utiliser `_environ` ou `_wenviron` pour accéder aux informations d'environnement.  Pour plus d'informations sur la relation liant `_putenv` et `_wputenv` aux variables globales, consultez [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Les familles de fonctions `_putenv` et `_getenv` ne sont pas sécurisées du point de vue du thread.  `_getenv` peut retourner un pointeur de chaîne alors que `_putenv` modifie la chaîne, provoquant des défaillances aléatoires.  Assurez\-vous que les appels à ces fonctions sont synchronisés.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h\>|  
|`_wputenv`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Pour obtenir un exemple de la façon d'utiliser `_putenv`, consultez [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)