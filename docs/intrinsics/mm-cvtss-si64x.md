---
title: _mm_cvtss_si64x | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_cvtss_si64x
dev_langs: C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f55ecac0a9f6318b5d60a372003e548ce41c713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Section spécifique à Microsoft**  
  
 Génère le [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] version étendue de la convertir scalaire unique précision nombre à virgule flottante à entier 64 bits (`cvtss2si`) instruction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `value`  
 Un `__m128` structure contenant les valeurs à virgule flottante-.  
  
## <a name="return-value"></a>Valeur de retour  
 Un entier 64 bits, le résultat de la conversion de la première valeur à virgule flottante en un entier.  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Le premier élément de la valeur de la structure est converti en un entier et est retourné. Les bits de contrôle arrondi dans MXCSR permettent de déterminer le comportement d’arrondi. La valeur par défaut le mode d’arrondi est arrondi à la plus proche, arrondi au nombre pair si la partie décimale est 0,5. Étant donné que le `__m128` structure représente un registre XMM, cet intrinsèque prend une valeur du registre XMM et l’écrit dans la mémoire système.  
  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
## <a name="example"></a>Exemple  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__m128d](../cpp/m128d.md)   
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)