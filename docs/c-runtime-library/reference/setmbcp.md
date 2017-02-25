---
title: "_setmbcp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmbcp"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_setmbcp"
  - "setmbcp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setmbcp (fonction)"
  - "pages de codes multioctets"
  - "setmbcp (fonction)"
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _setmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit une nouvelle page de codes multioctets.  
  
## Syntaxe  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### Paramètres  
 `codepage`  
 Nouveaux paramètres de la page de codes pour les routines multioctets indépendantes des paramètres locaux.  
  
## Valeur de retour  
 Retourne 0 si la page de codes est définie correctement.  Si une valeur de page de codes est fournie pour `codepage`, retourne – 1 et les paramètres de la page de codes ne sont pas modifiés.  Définit `errno` à `EINVAL` en cas d'échec d'allocation de mémoire.  
  
## Notes  
 La fonction `_setmbcp` spécifie une nouvelle page de codes multioctets.  Par défaut, le système d'exécution définit automatiquement la page de codes multioctets à la page de codes ANSI du système DÉFAUT.  Les paramètres de la page de codes multioctets affectent toutes les routines multioctets qui ne sont pas dépendantes des paramètres locaux.  Toutefois, il est possible de demander à `_setmbcp` d'utiliser la page de codes définie pour les paramètres locaux actuels \(consultez la liste suivante de constantes manifestes et des résultats associés de comportement\).  Pour obtenir la liste des routines multioctets qui dépendent de la page de codes paramètres locaux plutôt que la page de codes multioctets, consultez [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 La page de codes multioctets affecte également le traitement de caractères multi\-octets par les routines suivantes de la bibliothèque d'exécutables :  
  
||||  
|-|-|-|  
|[fonctions de \_exec](../../c-runtime-library/exec-wexec-functions.md)|[\_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[\_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[fonctions de \_spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[\_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 En outre, toutes les routines de la bibliothèque d'exécutables qui recoivent le caractère multioctet `argv` dou les arguments du programme `envp` \(comme les familles `_exec` et `_spawn` \) traitent ces chaînes en fonction de la page de codes multioctets.  Par conséquent, ces routines sont également affectées par un appel à `_setmbcp` qui modifie la page de codes multioctets.  
  
 La propriété `codepage` peut être définie à n'importe laquelle des valeurs suivantes.  
  
-   `_MB_CP_ANSI` Utilisez la Page de codes ANSI extraite du système d'exploitation au démarrage du programme.  
  
-   `_MB_CP_LOCALE` Utilisez la page de codes des paramètres régionaux obtenue à partir d'un appel précédent à [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   `_MB_CP_OEM` Utilisez la page de code OEM extraite du système d'exploitation au démarrage du programme.  
  
-   `_MB_CP_SBCS` Utilisez la page de codes codés sur un octet.  Lorsque la page de codes est définie à `_MB_CP_SBCS`, une routine par exemple [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) retourne toujours la valeur false.  
  
-   Toute autre page de codes valide, que la valeur soit ANSI,OEM ou bien encore celle d'une autre page de code supportée par le système d'exploitation \(sauf UTF\-7 et UTF\-8, qui ne sont pas supportés\).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)