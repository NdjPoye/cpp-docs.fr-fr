---
title: "Plage de valeurs enti&#232;res | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Plage de valeurs enti&#232;res
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** Représentations et jeux de valeurs des différents types d'entiers  
  
 Les entiers contiennent 32 bits \(quatre octets\).  Les entiers signés sont représentés sous la forme d'un complément à deux.  Le bit le plus significatif indique le signe : 1 pour les nombres négatifs, 0 pour les nombres positifs et zéro.  Les valeurs sont répertoriées ci\-dessous :  
  
|Type|Minimum et maximum|  
|----------|------------------------|  
|**unsigned short**|de 0 à 65535|  
|`signed short`|de –32768 à 32767|  
|`unsigned long`|0 à 4294967295|  
|**signed long**|de –2147483648 à 2147483647|  
  
## Voir aussi  
 [Entiers](../c-language/integers.md)