---
title: _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
dev_langs:
- C++
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 64a3e897179f22c327a88c4b6a35361341685d17
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
**Fonctions spécifiques à la page de codes 932**  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _ismbchira(  
   unsigned int c   
);  
int _ismbchira_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbckata(  
   unsigned int c   
);  
int _ismbckata_l(  
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
  
|Routine|Condition de test (page de codes 932 uniquement)|  
|-------------|-------------------------------------------|  
|`_ismbchira`|Hiragana sur deux octets : 0x829F<=`c`<=0x82F1.|  
|`_ismbchira_l`|Hiragana sur deux octets : 0x829F<=`c`<=0x82F1.|  
|`_ismbckata`|Hiragana sur deux octets : 0x8340<=`c`<=0x8396.|  
|`_ismbckata_l`|Hiragana sur deux octets : 0x8340<=`c`<=0x8396.|  
  
 **Fin des fonctions spécifiques à la page de codes 932**  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_ismbchira`|\<mbstring.h>|  
|`_ismbchira_l`|\<mbstring.h>|  
|`_ismbckata`|\<mbstring.h>|  
|`_ismbckata_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
