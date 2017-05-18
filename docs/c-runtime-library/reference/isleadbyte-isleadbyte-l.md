---
title: isleadbyte, _isleadbyte_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isleadbyte_l
- isleadbyte
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
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 73078df22931a5533ffe912174d11b384c8de417
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
Détermine si un caractère est l’octet de tête d’un caractère multioctet.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez                  [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Entier à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 `isleadbyte` retourne une valeur différente de zéro si l’argument satisfait à la condition de test, ou 0 si ce n’est pas le cas. Dans les paramètres régionaux « C » et dans les paramètres régionaux SBCS (jeu de caractères codés sur un octet), `isleadbyte` retourne toujours 0.  
  
## <a name="remarks"></a>Notes  
 La macro `isleadbyte` retourne une valeur différente de zéro si son argument est le premier octet d’un caractère multioctet. `isleadbyte`produit un résultat significatif pour n’importe quel argument entier compris entre -1 (`EOF`) à `UCHAR_MAX` (0xFF), inclus.  
  
 Le type d’argument attendu de `isleadbyte` est `int`. Si un caractère signé est passé, le compilateur est susceptible de le convertir en un entier par extension de signe, aboutissant à des résultats imprévisibles.  
  
 La version de cette fonction avec le suffixe `_l` est identique, excepté qu’il utilise les paramètres régionaux passés au lieu des paramètres régionaux actuels pour son comportement dépendant des paramètres régionaux.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|Retourne toujours la valeur false|**_** `isleadbyte`|Retourne toujours la valeur false|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classification d’octet](../../c-runtime-library/byte-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [_ismbb Routines](../../c-runtime-library/ismbb-routines.md)
