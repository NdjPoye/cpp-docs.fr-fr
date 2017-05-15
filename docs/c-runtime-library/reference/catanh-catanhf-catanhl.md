---
title: catanh, catanhf, catanhl | Microsoft Docs
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
- catanh
- catanhf
- catanhl
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
- catanh
- catanhf
- catanhl
- complex/catanh
- complex/catanhf
- complex/catanhl
dev_langs:
- C++
helpviewer_keywords:
- catanh function
- catanhf function
- catanhl function
ms.assetid: 1b6021cb-647a-41b4-9d7f-919cc8b57b86
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
ms.openlocfilehash: c70314e30419f6315fc1c3afe84e8e9fc104d728
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="catanh-catanhf-catanhl"></a>catanh, catanhf, catanhl
Récupère la tangente hyperbolique inverse d’un nombre complexe, avec des coupes de branche en dehors de l’intervalle [-1 ; + 1] sur l’axe réel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_Dcomplex catanh(   
   _Dcomplex z   
);  
_Fcomplex catanh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex catanh(   
   _Lcomplex z   
);  //  C++ only  
_Fcomplex catanhf(   
   _Fcomplex z   
);  
_Lcomplex catanhl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `z`  
 Nombre complexe qui représente un angle, en radians.  
  
## <a name="return-value"></a>Valeur de retour  
 Tangente hyperbolique inverse de `z`, en radians. Le résultat est illimité sur l’axe réel, ainsi que dans l’intervalle [-iπ/2 ; + iπ/2] sur l’axe imaginaire. Une erreur de domaine se produit si `z` est en dehors de l’intervalle [-1, +1]. Une erreur de pôle se produit si `z` est -1 ou +1.  
  
## <a name="remarks"></a>Notes  
 C++ autorisant la surcharge, vous pouvez appeler des surcharges de `catanh` qui acceptent et retournent des valeurs `_Fcomplex` et `_Lcomplex`. Dans un programme C, `catanh` accepte et retourne toujours une valeur `_Dcomplex` .  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête C|En-tête C++|  
|-------------|--------------|------------------|  
|`catanh`,               `catanhf`, `catanhl`|\<complex.h>|\<ccomplex>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)
