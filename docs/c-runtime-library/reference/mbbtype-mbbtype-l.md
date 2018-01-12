---
title: _mbbtype, _mbbtype_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs: C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae66b1c0765f496dcfe460c4ea7ff4f84e9333ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l
Retourne le type d'octet en se basant sur l'octet précédent.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à tester.  
  
 `type`  
 Type d'octet à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `_mbbtype` retourne le type d'octet dans une chaîne. Cette décision tient compte du contexte, tel que spécifié par la valeur de `type`, qui fournit la condition du test de contrôle. `type` est le type de l'octet précédent dans la chaîne. Les constantes manifestes présentes dans le tableau suivant sont définies dans Mbctype.h.  
  
|Valeur de `type`|`_mbbtype` teste la présence de|Valeur de retour|`c`|  
|---------------------|--------------------------|------------------|---------|  
|Toute valeur sauf 1|Octet unique ou octet de tête valide|`_MBC_SINGLE` (0)|Octet unique (0 x 20 – 0x7E, 0xA1 - 0xDF)|  
|Toute valeur sauf 1|Octet unique ou octet de tête valide|`_MBC_LEAD` (1)|Octet de caractère multioctet en tête (0 x 81 - 0x9F, 0xE0 - 0xFC)|  
|Toute valeur sauf 1|Octet unique ou octet de tête valide|`_MBC_ILLEGAL`<br /><br /> ( -1)|Caractère non valide (toute valeur sauf 0 x 20 – 0x7E, 0xA1 - 0xDF, 0 x 81 - 0x9F, 0xE0 - 0xFC|  
|1|Octet de fin valide|`_MBC_TRAIL` (2)|Fin des octets de caractères multioctets (0 x 40 - 0x7E, 0 x 80 - 0xFC)|  
|1|Octet de fin valide|`_MBC_ILLEGAL`<br /><br /> ( -1)|Caractère non valide (toute valeur sauf 0 x 20 – 0x7E, 0xA1 - 0xDF, 0 x 81 - 0x9F, 0xE0 - 0xFC|  
  
## <a name="remarks"></a>Notes  
 La fonction `_mbbtype` détermine le type d'un octet dans un caractère multioctet. Si la valeur de `type` est une valeur différente de 1, `_mbbtype` teste la présence d'un octet unique ou d'un octet de tête valide dans un caractère multioctet. Si la valeur de `type` est égale à 1, `_mbbtype` teste la présence d'un octet de fin valide dans un caractère multioctet.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). La version `_mbbtype` de cette fonction utilise les paramètres régionaux actifs pour ce comportement dépendant des paramètres régionaux ; la version `_mbbtype_l` est identique, sauf qu'elle utilise à la place les paramètres régionaux qui sont passés. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
 Dans les versions antérieures, `_mbbtype` était nommé `chkctype`. Pour le nouveau code, utilisez `_mbbtype`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* Pour les définitions des constantes manifestes utilisées comme valeurs de retour.  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classification d’octet](../../c-runtime-library/byte-classification.md)