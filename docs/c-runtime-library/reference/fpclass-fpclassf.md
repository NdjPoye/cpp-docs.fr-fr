---
title: _fpclass, _fpclassf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
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
ms.openlocfilehash: 9f061841ea6f4050945caeb2cacb9acfdce77c44
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
Retourne une valeur indiquant la classification à virgule flottante de l’argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>Paramètres  
 `x`  
 Valeur à virgule flottante à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 Les fonctions `_fpclass` et `_fpclassf` retournent une valeur entière qui indique la classification à virgule flottante de l’argument `x`. La classification peut avoir une des valeurs suivantes, définies dans \<float.h>.  
  
|Valeur|Description|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|NaN signalant|  
|`_FPCLASS_QNAN`|NaN silencieux|  
|`_FPCLASS_NINF`|Infini négatif (-INF)|  
|`_FPCLASS_NN`|Valeur non nulle normalisée négative|  
|`_FPCLASS_ND`|Valeur dénormalisée négative|  
|`_FPCLASS_NZ`|Un zéro négatif (- 0)|  
|`_FPCLASS_PZ`|Zéro positif (+0)|  
|`_FPCLASS_PD`|Valeur dénormalisée positive|  
|`_FPCLASS_PN`|Valeur non nulle normalisée positive|  
|`_FPCLASS_PINF`|Infini positif (+INF)|  
  
## <a name="remarks"></a>Notes  
 Les fonctions `_fpclass` et `_fpclassf` sont des fonctions fournies par Microsoft. Elles sont similaires à [fpclassify](../../c-runtime-library/reference/fpclassify.md), mais retournent des informations plus détaillées sur l’argument. La fonction `_fpclassf` n’est disponible que quand elle est compilée pour la plateforme x64.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 Pour plus d’informations sur la compatibilité et la conformité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)
