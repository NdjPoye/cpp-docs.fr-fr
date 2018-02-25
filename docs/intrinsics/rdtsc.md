---
title: __rdtsc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcf10bebb17096f29e2c96c9d66c631598d023aa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="rdtsc"></a>__rdtsc
**Section spécifique à Microsoft**  
  
 Génère le `rdtsc` instruction, qui retourne l’horodatage du processeur. L’horodatage de processeur enregistre le nombre de cycles d’horloge depuis la dernière réinitialisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Entier non signé 64 bits représentant le nombre de cycles.  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Cette routine est disponible uniquement en tant qu’intrinsèque.  
  
 L’interprétation de la valeur TSC dans cette génération de matériel diffère de celui des versions antérieures de [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]. Consultez les manuels de matériel pour plus d’informations.  
  
## <a name="example"></a>Exemple  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)