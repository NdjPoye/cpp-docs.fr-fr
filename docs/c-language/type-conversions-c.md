---
title: "Conversions de type (C) | Microsoft Docs"
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
  - "conversions, type"
  - "convertir des types"
  - "promotions d'un intégral"
  - "casts de type, lors de l'exécution"
  - "conversion de type"
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversions de type (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les conversions de type dépendent de l'opérateur spécifié et du type de l'opérande ou des opérateurs.  Les conversions de type sont effectuées dans les cas suivants :  
  
-   Lorsqu'une valeur d'un type est assignée à une variable d'un type différent ou qu'un opérateur convertit le type de son opérande ou de ses opérandes avant d'exécuter une opération  
  
-   Lorsqu'une valeur d'un type est explicitement convertie en un type différent  
  
-   Lorsqu'une valeur est passée comme argument à une fonction ou lorsqu'un type est retourné depuis une fonction  
  
 Un caractère, un entier court ou un champ de bits entier, tous signés ou non signés, ou un objet de type énumération, peuvent être utilisés dans une expression partout où un entier peut être utilisé.  Si `int` peut représenter toutes les valeurs du type d'origine, la valeur est convertie en `int` ; sinon, elle est convertie en `unsigned int`.  Ce processus porte le nom de « promotion d'un intégral ». Les promotions d'un intégral conservent la valeur.  Autrement dit, vous pouvez être sûr que la valeur après la promotion est identique à celle précédant la promotion.  Pour plus d'informations, consultez [Conversions arithmétiques ordinaires](../c-language/usual-arithmetic-conversions.md).  
  
## Voir aussi  
 [Expressions et assignations](../c-language/expressions-and-assignments.md)