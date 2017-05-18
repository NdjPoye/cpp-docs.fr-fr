---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
- _ismbcupper
- _ismbclower
dev_langs:
- C++
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
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
ms.openlocfilehash: 2d62b6859490047796d66cc2b56090a130ffd5f9
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
Vérifie si un caractère multioctet est un caractère minuscule ou majuscule.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si le caractère satisfait à la condition de test ou 0 dans le cas contraire. Si `c` est inférieur ou égal à 255 et qu’il existe une routine `_ismbb` correspondante (par exemple, `_ismbcalnum` correspond à `_ismbbalnum`), le résultat est la valeur de retour de la routine `_ismbb` correspondante.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions teste un caractère multioctet fourni pour un état donné.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|--------------------|---------------------------|  
|`_ismbclower`|Caractère alphabétique minuscule|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais minuscule ASCII : 0x61<=`c`<=0x7A.|  
|`_ismbclower_l`|Caractère alphabétique minuscule|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais minuscule ASCII : 0x61<=`c`<=0x7A.|  
|`_ismbcupper`|Caractère alphabétique majuscule|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais majuscule ASCII : 0x41<=`c`<=0x5A.|  
|`_ismbcupper_l`|Caractère alphabétique majuscule|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais majuscule ASCII : 0x41<=`c`<=0x5A.|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_ismbclower`|\<mbstring.h>|  
|`_ismbclower_l`|\<mbstring.h>|  
|`_ismbcupper`|\<mbstring.h>|  
|`_ismbcupper_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb, routines](../../c-runtime-library/ismbb-routines.md)
