---
title: "Types d&#39;entier | Microsoft Docs"
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
  - "constantes entières"
  - "integer (type de données), types d'entier en C++"
  - "types d'entier"
  - "entiers, types"
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Types d&#39;entier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque constante entière reçoit un type selon sa valeur et la façon dont elle est exprimée.  Vous pouvez forcer une constante entière à être de type **long** en ajoutant la lettre **l** ou **L** à la fin de la constante ; vous pouvez la forcer à être de type `unsigned` en ajoutant **u** ou **R** à la valeur.  La minuscule **l** peut être confondue avec le chiffre 1 et doit être évitée.  Voici certaines formes de constantes entières **long** :  
  
```  
/* Long decimal constants */  
10L  
79L  
  
/* Long octal constants */  
012L  
0115L  
  
/* Long hexadecimal constants */  
0xaL or 0xAL  
0X4fL or 0x4FL  
  
/* Unsigned long decimal constant */  
776745UL  
778866LU  
```  
  
 Le type que vous assignez à une constante dépend de la valeur que cette constante représente.  La valeur d'une constante doit être dans la plage de valeurs pouvant être représentées pour son type.  Le type d'une constante détermine quelles conversions sont exécutées lorsque la constante est utilisée dans une expression ou lorsque le signe moins \(**–**\) est appliqué.  La liste suivante résume les règles de conversion des constantes entières.  
  
-   Le type d'une constante décimale sans suffixe est `int`, **long int** ou **unsigned long int**.  Le premier de ces trois types dans lesquels la valeur de la constante peut être représentée est le type assigné à la constante.  
  
-   Le type assigné à des constantes octales et hexadécimales sans suffixes est `int`, `unsigned int`, **long int**, ou **unsigned long int** , selon la taille de la constante.  
  
-   Le type assigné aux constantes ayant pour suffixe **u** ou **U** est **unsigned int** ou **unsigned long int** ,selon leur taille.  
  
-   Le type assigné aux constantes ayant pour suffixe **l** ou **L** est **long int** ou **unsigned long int** , selon leur taille.  
  
-   Le type assigné aux constantes ayant pour suffixe **u** ou **U** et **l** ou **L** est **unsigned long int**.  
  
## Voir aussi  
 [Constantes entières C](../c-language/c-integer-constants.md)