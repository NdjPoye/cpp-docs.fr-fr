---
title: "Types scalaires | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Types scalaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Même si l'accès aux données peut provenir d'un alignement quelconque, il est recommandé d'aligner les données sur leur limite naturelle afin d'éviter une ou plusieurs pertes de performances.  Les enums sont des entiers constants traités comme des entiers de 32 bits.  Le tableau suivant décrit la définition de type et le stockage recommandé pour celle\-ci en ce qui concerne l'alignement à l'aide des valeurs d'alignement suivantes :  
  
-   Byte – 8 bits  
  
-   Word – 16 bits  
  
-   Double Word – 32 bits  
  
-   Quad Word – 64 bits  
  
-   Octa Word – 128 bits  
  
|||||  
|-|-|-|-|  
|Type scalaire|Type de données C|Taille de stockage \(en octets\)|Alignement recommandé|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int, long**|4|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|4|Doubleword|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned \_\_int64**|8|Quadword|  
|**FP32 \(simple précision\)**|**float**|4|Doubleword|  
|**FP64 \(double précision\)**|**double**|8|Quadword|  
|**POINTER**|**\***|8|Quadword|  
|`__m64`|**struct \_\_m64**|8|Quadword|  
|`__m128`|**struct \_\_m128**|16|Octaword|  
  
## Voir aussi  
 [Types et stockage](../build/types-and-storage.md)