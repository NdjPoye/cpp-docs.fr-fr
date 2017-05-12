---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
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
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
dev_langs:
- C++
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
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
ms.openlocfilehash: b8e39939471e6f1761b6936a215bb8a1e4e13d8c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ismbcalnum-ismbcalnuml-ismbcalpha-ismbcalphal-ismbcdigit-ismbcdigitl"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
Vérifie si un caractère multioctet est un caractère alphanumérique, alphabétique ou numérique.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _ismbcalnum  
(  
   unsigned int c   
);  
int _ismbcalnum_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcalpha  
(  
   unsigned int c   
);  
int _ismbcalpha_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcdigit  
(  
   unsigned int c   
);  
int _ismbcdigit_l  
(  
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
 Chacune de ces routines teste un caractère multioctet fourni pour un état donné.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|--------------------|---------------------------|  
|`_ismbcalnum,_ismbcalnum_l`|Alphanumérique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais ASCII : consultez les exemples pour `_ismbcdigit` et `_ismbcalpha`.|  
|`_ismbcalpha,_ismbcalpha_l`|Alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’une lettre de l’alphabet anglais ASCII : 0x41<=`c`<=0x5A ou 0x61<=`c`<=0x7A ; ou une lettre katakana : 0xA6<=`c`<=0xDF.|  
|`_ismbcdigit,_ismbcdigit`|Chiffre|Retourne une valeur différente de zéro si et seulement si `c` est une représentation sur un octet d’un chiffre ASCII : 0x30<=`c`<=0x39.|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_ismbcalnum,_ismbcalnum_l`|\<mbstring.h>|  
|`_ismbcalpha,_ismbcalpha_l`|\<mbstring.h>|  
|`_ismbcdigit,_ismbcdigit_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb, routines](../../c-runtime-library/ismbb-routines.md)
