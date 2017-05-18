---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs:
- C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
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
ms.openlocfilehash: 33949110690ef671a7a2b0d40e98f81c9d7fbc2f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l
Convertit un caractère en minuscule.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `c`  
 Caractère à convertir.  
  
 [in] `locale`  
 Paramètres régionaux à utiliser pour une traduction spécifique aux paramètres régionaux.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces routines convertit une copie de `c` en minuscule si la conversion est possible, et retourne le résultat. Il n’existe aucune valeur de retour réservée pour indiquer une erreur.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces routines convertit une lettre majuscule donnée en lettre minuscule si cela est possible et approprié. La conversion de la casse de `towlower` est spécifique aux paramètres régionaux. Seuls les caractères relevant des paramètres régionaux actifs changent de casse. Les fonctions sans suffixe `_l` utilisent les paramètres régionaux actuellement définis. Les versions de ces fonctions avec suffixe `_l` prennent les paramètres régionaux comme paramètre et les utilisent à la place des paramètres régionaux actuellement définis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Pour que `_tolower` donne les résultats attendus, [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) et [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) doivent retourner une valeur différente de zéro.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
> Les routines  `_tolower_l` et `_towlower_l` ne dépendent pas des paramètres régionaux et ne sont pas destinées à être appelées directement. Elles sont fournies pour une utilisation en interne par `_totlower_l`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`tolower`|\<ctype.h>|  
|`_tolower`|\<ctype.h>|  
|`towlower`|\<ctype.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple dans [to, fonctions](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [to, fonctions](../../c-runtime-library/to-functions.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
