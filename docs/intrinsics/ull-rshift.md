---
title: "__ull_rshift | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ull_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ull_rshift, intrinsèque"
  - "__ull_rshift, intrinsèque"
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ull_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 sur x64, décalages une valeur 64 bits spécifié par le premier paramètre vers la droite selon un certain nombre de bits spécifié par le deuxième paramètre.  
  
## Syntaxe  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### Paramètres  
 \[in\] `mask`  
 La valeur entière 64 bits pour déplacer la droite.  
  
 \[in\] `nBit`  
 Le nombre de bits à déplacer, du modulo 32 sur x86, et du modulo 64 sur x64.  
  
## Valeur de retour  
 Le masque déplacé par les bits d' `nBit` .  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Si le deuxième paramètre est supérieur à 31 sur les ordinateurs x86 \(63 sur x64\), ce nombre est le modulo pris 32 \(64 sous x64\) pour déterminer le nombre de bits pour déplacer.  `ull` dans l'étiquette indique `unsigned long long (unsigned __int64)`.  
  
## Exemple  
  
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
  
## Sortie  
  
```  
1  
```  
  
### détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)