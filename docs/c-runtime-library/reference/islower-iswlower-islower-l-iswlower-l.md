---
title: islower, iswlower, _islower_l, _iswlower_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswlower
- _islower_l
- islower
- _iswlower_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istlower
- islower
- _ismbclower_l
- _liswlower_l
- _istlower_l
- _iswlower_l
- _islower _l
- _islower_l
- iswlower
dev_langs: C++
helpviewer_keywords:
- _islower _l function
- _ismbclower_l function
- islower function
- _iswlower_l function
- _liswlower_l function
- _istlower_l function
- istlower function
- _istlower function
- iswlower function
- _islower_l function
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6aa6f584db325694b081f367f8b78146776764ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="islower-iswlower-islowerl-iswlowerl"></a>islower, iswlower, _islower_l, _iswlower_l
Détermine si un entier représente un caractère minuscule.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int islower(  
   int c   
);  
int iswlower(  
   wint_t c   
);  
int islower_l(  
   int c,  
   _locale_t locale  
);  
int _iswlower_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si `c` est une représentation particulière d’un caractère minuscule. `islower`Retourne une valeur différente de zéro si `c` est un caractère en minuscule (a - z). `iswlower` retourne une valeur différente de zéro si `c` est un caractère large qui correspond à une lettre minuscule, ou si `c` appartient à un jeu de caractères larges défini par l’implémentation pour lequel aucun des éléments `iswcntrl`, `iswdigit`, `iswpunct` ou `iswspace` n’est différent de zéro. Chacune de ces routines retourne 0 si `c` ne répond pas à la condition de test.  
  
 Pour leur comportement dépendant des paramètres régionaux, les versions de ces fonctions avec le suffixe `_l` utilisent les paramètres régionaux qui sont passés au lieu des paramètres régionaux actuels. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
 Le comportement de `islower` et `_islower_l` n’est pas défini si `c` n’est pas EOF ou n’appartient pas à la plage 0 à 0xFF, inclus. Quand une bibliothèque CRT de débogage est utilisée et que `c` ne fait pas partie de ces valeurs, les fonctions déclenchent une assertion.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istlower`|`islower`|[_ismbclower](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswlower`|  
|`_istlower_l`|`_islower _l`|[_ismbclower_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_liswlower_l`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`islower`|\<ctype.h>|  
|`iswlower`|\<ctype.h> ou \<wchar.h>|  
|`_islower_l`|\<ctype.h>|  
|`_swlower_l`|\<ctype.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)