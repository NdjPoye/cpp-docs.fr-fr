---
title: "Conversion &#224; partir d&#39;autres types | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "casts de type, conversion"
  - "valeurs, convertir"
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conversion &#224; partir d&#39;autres types
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme une valeur `enum` est une valeur `int` par définition, les conversions vers et depuis une valeur `enum` sont les mêmes que celles du type `int`.  Pour le compilateur Microsoft C, un entier est identique à une valeur **long**.  
  
 **Section spécifique à Microsoft**  
  
 Aucune conversion entre les types structure ou union n'est autorisée.  
  
 Toute valeur peut être convertie vers le type `void`, mais le résultat d'une telle conversion peut être utilisé uniquement dans un contexte où une valeur d'expression est ignorée, comme dans une instruction d'expression.  
  
 Le type `void` n'a aucune valeur, par définition.  Par conséquent, il ne peut pas être converti vers un autre type et les autres types ne peuvent pas être convertis vers `void` par assignation.  Toutefois, vous pouvez effectuer un cast explicite d'une valeur vers le type `void`, comme cela est expliqué dans [Conversions de cast de type](../c-language/type-cast-conversions.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Conversions d'assignation](../c-language/assignment-conversions.md)