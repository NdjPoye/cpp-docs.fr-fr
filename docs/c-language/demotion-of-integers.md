---
title: "R&#233;trogradation des entiers | Microsoft Docs"
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
  - "rétrograder des entiers"
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# R&#233;trogradation des entiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.2.1.2** Le résultat de la conversion d'un entier en un entier signé plus court, ou le résultat de la conversion d'un entier non signé en entier signé de longueur égale si la valeur ne peut pas être représentée  
  
 Lorsqu'un entier **long** est casté en un **short** ou qu'un **short** est casté en un `char`, les octets moins significatifs sont conservés.  
  
 Par exemple, cette ligne  
  
```  
short x = (short)0x12345678L;  
```  
  
 assigne la valeur 0x5678 à `x`, et cette ligne  
  
```  
char y = (char)0x1234;  
```  
  
 assigne la valeur 0x34 à `y`.  
  
 Lorsque des variables signées sont converties en variables non signées et vice versa, les modèles binaires restent les mêmes.  Par exemple, le cast de – 2 \(0xFE\) en une valeur non signée produit 254 \(également 0xFE\).  
  
## Voir aussi  
 [Entiers](../c-language/integers.md)