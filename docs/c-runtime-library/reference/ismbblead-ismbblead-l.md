---
title: _ismbblead, _ismbblead_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbblead_l
- _ismbblead
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
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
dev_langs:
- C++
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 187561adb3c524e12a851e0537859f0be942be17
ms.lasthandoff: 02/24/2017

---
# <a name="ismbblead-ismbbleadl"></a>_ismbblead, _ismbblead_l
Teste un caractère pour déterminer s’il s’agit d’un octet de tête d’un caractère multioctet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne une valeur différente de zéro si l’entier `c` est le premier octet d’un caractère multioctet.  
  
## <a name="remarks"></a>Notes  
 Les caractères multioctets sont constitués d’un octet de tête suivi d’un octet de fin. Les octets de tête se distinguent en faisant partie d’une plage particulière pour un jeu de caractères donné. Par exemple, dans la page de codes 932 uniquement, les octets de tête sont compris entre 0x81 - 0x9F et 0xE0 - 0xFC.  
  
 `_ismbblead` utilise les paramètres régionaux actuels pour le comportement dépendant des paramètres régionaux. `_ismbblead_l` est identique, excepté qu’il utilise à la place les paramètres régionaux passés. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlead`|Retourne toujours la valeur false|`_ismbblead`|Retourne toujours la valeur false|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_ismbblead`|\<mbctype.h> ou \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
|`_ismbblead_l`|\<mbctype.h> ou \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
  
 \* Pour les constantes manifestes des conditions de test.  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Classification d’octet](../../c-runtime-library/byte-classification.md)   
 [_ismbb, routines](../../c-runtime-library/ismbb-routines.md)
