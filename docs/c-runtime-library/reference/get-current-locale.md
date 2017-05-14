---
title: _get_current_locale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: e2f14ad541750967d63a50c13ec82a9ed57fce05
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="getcurrentlocale"></a>_get_current_locale
Obtient un objet de paramètres régionaux qui représente les paramètres régionaux actuels.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Objet de paramètres régionaux qui représente les paramètres régionaux actuels.  
  
## <a name="remarks"></a>Remarques  
 Le `_get_current_locale` fonction obtient actuellement défini les paramètres régionaux du thread et retourne un objet de paramètres régionaux qui représente les paramètres régionaux.  
  
 Le nom précédent de cette fonction, `__get_current_locale` (avec deux traits de soulignement de début), a été déconseillé.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)
