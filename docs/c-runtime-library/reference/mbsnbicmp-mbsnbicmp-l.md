---
title: _mbsnbicmp, _mbsnbicmp_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16f4125727177b4bb32730aabe2ec0798ca1b622
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l
Compare `n` octets de deux chaînes de caractères multioctets, en ignorant la casse.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez [fonctions CRT non prises en charge dans les applications de plateforme Windows universelle](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `string1, string2`  
 Chaîne terminée par Null à comparer.  
  
 `count`  
 Nombre d'octets à comparer.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour indique la relation entre les sous-chaînes.  
  
|Valeur de retour|Description|  
|------------------|-----------------|  
|< 0|La sous-chaîne de `string1` est inférieure à la sous-chaîne de `string2`.|  
|0|La sous-chaîne de `string1` est identique à la sous-chaîne de `string2`.|  
|> 0|La sous-chaîne de `string1` est supérieure à la sous-chaîne de `string2`.|  
  
 En cas d'erreur, `_mbsnbcmp` retourne `_NLSCMPERROR`, qui est défini dans String.h et Mbstring.h.  
  
## <a name="remarks"></a>Notes  
 La fonction `_mbsnbicmp` effectue une comparaison ordinale des `count` (au plus) premiers octets de `string1` et de `string2`. La comparaison est effectuée en convertissant chaque caractère en minuscule ; `_mbsnbcmp` est une version de `_mbsnbicmp` qui respecte la casse. La comparaison se termine si un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés. Si les chaînes sont égales quand un caractère null de fin est atteint dans l'une ou l'autre des chaînes avant que `count` caractères soient comparés, la chaîne la plus courte est considérée comme étant inférieure.  
  
 `_mbsnbicmp` est similaire à `_mbsnicmp`, à ceci près qu’elle compare des chaînes jusqu’à `count` octets au lieu de les comparer par caractères.  
  
 La comparaison de deux chaînes contenant des caractères qui se trouvent entre « Z » et « a » dans la table ASCII (« [ », « \\ », « ] », « ^ », « _ » et « \` ») donne des résultats différents selon leur casse. Par exemple, les deux chaînes « `ABCDE` » et « `ABCD^` » se comparent d'une certaine façon si la comparaison est en minuscules (« `abcde` » > « `abcd^` ») et d'une autre façon (« `ABCDE` » < « `ABCD^` ») si elle est en majuscules.  
  
 `_mbsnbicmp` reconnaît les séquences de caractères multioctets en fonction de la [page de codes multioctets](../../c-runtime-library/code-pages.md) en cours d’utilisation. Elle n'est pas affectée par les paramètres régionaux actuels.  
  
 Si `string1` ou `string2` est un pointeur null, `_mbsnbicmp` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, cette fonction retourne `_NLSCMPERROR` et définit à `errno` à `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbsnbicmp`|<mbstring.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)