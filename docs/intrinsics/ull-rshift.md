---
title: __ull_rshift | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0193bad5b9184e3168c618b9bc4e3afc5e27abc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ullrshift"></a>__ull_rshift
**Section spécifique à Microsoft**  
  
 sur x64, déplace une valeur 64 bits spécifiée par le premier paramètre à droite d’un nombre de bits spécifié par le deuxième paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `mask`  
 La valeur d’entier 64 bits de décalage vers la droite.  
  
 [in] `nBit`  
 Le nombre de bits de décalage, modulo 32 sur x86 et modulo 64 sur x64.  
  
## <a name="return-value"></a>Valeur de retour  
 Le masque décale `nBit` bits.  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Si le deuxième paramètre est supérieur à 31 sur x86 (63 sur x64), ce nombre est effectuée modulo 32 (64 sur x64) pour déterminer le nombre de bits à décaler. Le `ull` dans le nom indique `unsigned long long (unsigned __int64)`.  
  
## <a name="example"></a>Exemple  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
1  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)