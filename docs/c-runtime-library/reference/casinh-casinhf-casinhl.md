---
title: casinh, casinhf, casinhl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- casinh
- casinhl
- casinhf
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
- casinh
- casinhf
- casinhl
- complex/casinh
- complex/casinhf
- complex/casinhl
dev_langs:
- C++
helpviewer_keywords:
- casinh function
- casinhf function
- casinhl function
ms.assetid: bd18340b-21dd-4c86-a14e-e8e15dd97e3b
caps.latest.revision: 10
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
ms.openlocfilehash: 1620eb200723fe4b2cd6553e7ba50405b026d53c
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="casinh-casinhf-casinhl"></a>casinh, casinhf, casinhl
Récupère le sinus hyperbolique inverse d’un nombre complexe, avec des coupes de branche en dehors de l’intervalle [-i, + i] sur l’axe imaginaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_Dcomplex casinh(   
   _Dcomplex z   
);  
_Fcomplex casinh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex casinh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex casinhf(   
   _Fcomplex z   
);  
_Lcomplex casinhl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `z`  
 Nombre complexe qui représente un angle, en radians.  
  
## <a name="return-value"></a>Valeur de retour  
 Sinus hyperbolique inverse de `z`, en radians. Le résultat est indépendant de l’axe réel, ainsi que dans l’intervalle [-iπ/2 + iπ/2] sur l’axe imaginaire.  
  
## <a name="remarks"></a>Remarques  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `casinh` qui acceptent et retournent des valeurs `_Fcomplex` et `_Lcomplex`. Dans un programme C, `casinh` accepte et retourne toujours une valeur `_Dcomplex` .  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête C|En-tête C++|  
|-------------|--------------|------------------|  
|`casinh`,               `casinhf`, `casinhl`|\<complex.h>|\<ccomplex>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)
