---
title: "__shiftright128 | Microsoft Docs"
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
  - "__shiftright128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__shiftright128 intrinsic"
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __shiftright128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Décale une quantité de 128 bits, représentée par deux quantités de 64 bits `LowPart` et `HighPart`, vers la droite d'un nombre de bits spécifié par `Shift` et retourne les 64 bits de poids faible du résultat.  
  
## Syntaxe  
  
```  
unsigned __int64 __shiftright128(     unsigned __int64 LowPart,     unsigned __int64 HighPart,     unsigned char Shift  );  
```  
  
#### Paramètres  
 \[in\] `LowPart`  
 64 bits de poids faible de la quantité de 128 bits à décaler.  
  
 \[in\] `HighPart`  
 64 bits de poids fort de la quantité de 128 bits à décaler.  
  
 \[in\] `Shift`  
 Nombre de bits à décaler.  
  
## Valeur de retour  
 64 bits de poids faible du résultat.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 La valeur `Shift` est toujours modulo 64 pour que, par exemple, si vous appelez `__shiftright128(0, 1, 64)`, la fonction décale les `0` bits de la partie supérieure vers la droite et renvoie une partie faible de `0` et non `1` comme on pourrait s'y attendre.  
  
## Exemple  
 Pour obtenir un exemple, consultez [\_\_shiftleft128](../intrinsics/shiftleft128.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\_\_shiftleft128](../intrinsics/shiftleft128.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)