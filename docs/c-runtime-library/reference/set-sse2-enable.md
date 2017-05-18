---
title: _set_SSE2_enable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_SSE2_enable
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
- _set_SSE2_enable
- set_SSE2_enable
dev_langs:
- C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6dcc32b981c73cda13152f82139a307e4739fe5c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="setsse2enable"></a>_set_SSE2_enable
Active ou désactive l’utilisation d’instructions SSE2 ([Streaming SIMD Extensions 2](http://msdn.microsoft.com/en-us/f98440eb-73a9-4f96-b203-ac41bb6701ea)) dans les routines mathématiques CRT. (Cette fonction n’est pas disponible dans les architectures x64, car SSE2 est activé par défaut.)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `flag`  
 1 pour activer l’implémentation SSE2 ; 0 pour désactiver l’implémentation SSE2. Par défaut, l’implémentation SSE2 est activée sur les processeurs qui la prennent en charge.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si l’implémentation SSE2 est activée ; zéro si l’implémentation SSE2 est désactivée.  
  
## <a name="remarks"></a>Notes  
 Les fonctions suivantes intègrent des implémentations SSE2 qui peuvent être activées à l’aide de `_set_SSE2_enable` :  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 Les implémentations SSE2 de ces fonctions peuvent donner des réponses légèrement différentes de celles apportées par les implémentations par défaut, car les valeurs intermédiaires SSE2 sont des quantités en virgule flottante de 64 bits, alors que les valeurs intermédiaires des implémentations par défaut sont des quantités en virgule flottante de 80 bits.  
  
> [!NOTE]
>  Si vous utilisez l’option du compilateur [/Oi (Générer des fonctions intrinsèques)](../../build/reference/oi-generate-intrinsic-functions.md) pour compiler le projet, `_set_SSE2_enable` peut sembler ne produire aucun effet. L’option du compilateur `/Oi` accorde à celui-ci le pouvoir d’utiliser des fonctions intrinsèques pour remplacer les appels CRT ; ce comportement se substitue à l’effet de `_set_SSE2_enable`. Si vous voulez faire en sorte que `/Oi` ne se substitue pas à `_set_SSE2_enable`, utilisez `/Oi-` pour compiler votre projet. Il peut aussi s’agir d’une bonne pratique quand vous utilisez d’autres commutateurs du compilateur qui font intervenir `/Oi`.  
  
 L’implémentation SSE2 n’est utilisée que si toutes les exceptions sont masquées. Pour masquer les exceptions, utilisez [_control87, _controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<math.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Sortie**  
  
 `SSE2 enabled.`  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctionnalités de bibliothèque CRT](../../c-runtime-library/crt-library-features.md)
