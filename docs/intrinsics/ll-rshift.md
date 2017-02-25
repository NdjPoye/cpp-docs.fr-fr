---
title: "__ll_rshift | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ll_rshift_cpp"
  - "__ll_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ll_rshift, intrinsèque"
  - "ll_rshift, intrinsèque"
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __ll_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Déplace une valeur 64 bits spécifié par le premier paramètre vers la droite selon un certain nombre de bits spécifié par le deuxième paramètre.  
  
## Syntaxe  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### Paramètres  
 \[in\] `Mask`  
 La valeur entière 64 bits pour déplacer la droite.  
  
 \[in\] `nBit`  
 Le nombre de bits à déplacer, du modulo 64 sur x64, et du modulo 32 sur x86.  
  
## Valeur de retour  
 Le masque déplacé par les bits d' `nBit` .  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Si le deuxième paramètre est supérieur à 64 sur 32 \(x64 sur x86\), ce nombre est le modulo pris 64 \(32 sur x86\) pour déterminer le nombre de bits pour déplacer.  Le préfixe d' `ll` indique qu'il s'agit d'une opération sur `long long`, un autre nom pour `__int64`, le type intégral signé 64 bits.  
  
## Exemple  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## Sortie  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **Remarque** si `_ull_rshift` a été utilisé, l'octet le plus significatif de la valeur droit\-déplacée aurait été zéro, l'effet souhaité n'aurait pas été obtenu dans le cas d'une valeur négative.  
  
### détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)