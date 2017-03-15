---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 60a870b9c0beff704511ab788d621b0f9697ed5d
ms.lasthandoff: 02/24/2017

---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
Convertit des caractères JIS (Japan Industry Standard) en caractères JMS(Microsoft Japan) ou des caractères JMS en caractères JIS.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à convertir.  
  
 `local`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Dans les paramètres régionaux japonais, ces fonctions retournent un caractère converti ou retournent 0 si aucune conversion n’est possible. Dans les paramètres régionaux non japonais, ces fonctions retournent le caractère passé.  
  
## <a name="remarks"></a>Notes  
 La fonction `_mbcjistojms` convertit un caractère JIS (Japan Industry Standard) en caractère Microsoft Kanji (Shift JIS). Le caractère n’est converti que si les octets de tête et de fin se trouvent dans la plage 0x21-0x7E. Si l’octet de tête ou de fin se trouve hors de cette plage, `errno` est défini sur `EILSEQ`. Pour plus d’informations sur ce code d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 La fonction `_mbcjmstojis` convertit un caractère Shift JIS en caractère JIS. Le caractère n’est converti que si l’octet de tête se trouve dans la plage 0x81-0x9F ou 0xE0-0xFC et l’octet de fin dans la plage 0x40-0x7E ou 0x80-0xFC. Notez que cette plage comporte certains codes de caractère auxquels aucun caractère n’est assigné et qui, de ce fait, ne peuvent pas être convertis.  
  
 La valeur `c` doit être une valeur 16 bits dont les 8 bits de poids fort représentent l’octet de tête du caractère à convertir et les 8 bits de poids faible l’octet de fin.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Dans les versions antérieures, `_mbcjistojms` et `_mbcjmstojis` s’appelaient `jistojms` et `jmstojis`, respectivement. `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` et `_mbcjmstojis_l` doivent être utilisées à la place.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h>|  
|`_mbcjistojms_l`|\<mbstring.h>|  
|`_mbcjmstojis`|\<mbstring.h>|  
|`_mbcjmstojis_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [_ismbb, routines](../../c-runtime-library/ismbb-routines.md)
