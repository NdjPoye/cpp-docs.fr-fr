---
title: "Conversions d&#39;assignation | Microsoft Docs"
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
helpviewer_keywords: 
  - "conversions d'assignation"
  - "conversions, d'assignation"
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversions d&#39;assignation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les opérations d'assignation, le type de la valeur assignée est converti en type de la variable qui reçoit l'assignation.  C permet des conversions par assignation entre les types intégraux et les types flottants, même si les informations sont perdues lors de la conversion.  La méthode de conversion utilisée dépend des types impliqués dans l'assignation, comme décrit dans [Conversions arithmétiques courantes](../c-language/usual-arithmetic-conversions.md) et dans les sections suivantes :  
  
-   [Conversions depuis les types intégraux signés](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Conversions depuis les types intégraux non signés](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Conversions depuis les types à virgule flottante](../c-language/conversions-from-floating-point-types.md)  
  
-   [Conversions vers et depuis les types pointeur](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Conversions depuis les autres types](../c-language/conversions-from-other-types.md)  
  
 Les qualificateurs de type n'affectent pas l'admissibilité de la conversion bien qu'il ne soit pas possible d'utiliser une l\-value **const** à gauche de l'assignation.  
  
## Voir aussi  
 [Conversions de type](../c-language/type-conversions-c.md)