---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
dev_langs:
- C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2da016750a125c6645a878b3fee04a09c3e76e26
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l
Convertit le caractère en majuscule.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à convertir.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces routines convertit une copie de `c`, si possible, et retourne le résultat.  
  
 Si `c` est un caractère large pour lequel `iswlower` a une valeur différente de zéro et s’il existe un caractère large correspondant pour lequel `iswupper` a une valeur différente de zéro, `towupper` retourne le caractère large correspondant ; sinon, `towupper` retourne `c` inchangé.  
  
 Il n’existe aucune valeur de retour réservée pour indiquer une erreur.  
  
 Pour que `toupper` donne les résultats attendus, [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) doivent retourner une valeur différente de zéro.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces routines convertit une lettre minuscule donnée en lettre majuscule si cela est possible et approprié. La conversion de la casse de `towupper` est spécifique aux paramètres régionaux. Seuls les caractères relevant des paramètres régionaux actifs changent de casse. Les fonctions sans suffixe `_l` utilisent les paramètres régionaux actuellement définis. Les versions de ces fonctions avec suffixe `_l` prennent les paramètres régionaux comme paramètre et les utilisent à la place des paramètres régionaux actuellement définis. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
 Pour que `toupper` donne les résultats attendus, [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) doivent retourner une valeur différente de zéro.  
  
 [Routines de conversion de données](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  Les routines `_toupper_l` et `_towupper_l` ne dépendent pas des paramètres régionaux et ne sont pas destinées à être appelées directement. Elles sont fournies pour une utilisation en interne par `_totupper_l`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`toupper`|\<ctype.h>|  
|`_toupper`|\<ctype.h>|  
|`towupper`|\<ctype.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple dans [to, fonctions](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [to, fonctions](../../c-runtime-library/to-functions.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)