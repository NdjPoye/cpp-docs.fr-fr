---
title: _setmbcp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4ae4dc9b57da5ee7d38f32066b8b4b204c50f065
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="setmbcp"></a>_setmbcp
Définit une nouvelle page de codes multioctets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `codepage`  
 Nouveau paramètre de page de codes pour les routines multioctets indépendantes des paramètres régionaux.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne 0 si la page de codes est correctement définie. Si une valeur de page de code non valide est fournie pour `codepage`, retourne -1 et le paramètre de la page de code est inchangée. Affecte à `errno` la valeur `EINVAL` en cas d’échec d’allocation de mémoire.  
  
## <a name="remarks"></a>Notes  
 La fonction `_setmbcp` spécifie une nouvelle page de codes multioctets. Par défaut, le système de runtime définit automatiquement la page de codes multioctets comme étant la page de codes ANSI par défaut du système. Le paramètre de page de codes multioctets influe sur toutes les routines multioctets qui ne sont pas dépendantes des paramètres régionaux. Cependant, il est possible de donner instruction à `_setmbcp` d’utiliser la page de codes définie pour les paramètres régionaux (consultez la liste de constantes manifestes suivante, ainsi que les résultats associés sur le plan du comportement). Pour obtenir la liste des routines multioctets qui dépendent de la page de codes des paramètres régionaux et non de la page de codes multioctets, consultez [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 La page de codes multioctets a aussi un impact sur le traitement des caractères multioctets assuré par les routines de bibliothèque Runtime suivantes :  
  
||||  
|-|-|-|  
|[fonctions _exec](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[fonctions _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 De plus, toutes les routines de bibliothèque runtime qui reçoivent des arguments de programme `argv` ou `envp` à caractères multioctets en tant que paramètres (tels que les familles `_exec` et `_spawn`) traitent ces chaînes d’après la page de codes multioctets. Par conséquent, ces routines sont aussi affectées par un appel à `_setmbcp` qui change de page de codes multioctets.  
  
 L’argument `codepage` peut être défini avec l’une des valeurs suivantes :  
  
-   `_MB_CP_ANSI` Utilise la page de codes ANSI obtenue du système d’exploitation au démarrage du programme.  
  
-   `_MB_CP_LOCALE` Utilise la page de codes des paramètres régionaux actifs obtenue d’un appel précédent à [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
-   `_MB_CP_OEM` Utilise la page de codes OEM obtenue du système d’exploitation au démarrage du programme.  
  
-   `_MB_CP_SBCS` Utilise la page de codes à octet unique. Quand la page de codes est définie avec `_MB_CP_SBCS`, une routine telle que [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) retourne toujours false.  
  
-   N’importe quelle autre valeur de page de codes valide, que ce soit ANSI, OEM ou toute autre page de codes prise en charge par le système d’exploitation (à l’exception de UTF-7 et UTF-8, qui ne sont pas pris en charge).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_setmbcp`|\<mbctype.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)
