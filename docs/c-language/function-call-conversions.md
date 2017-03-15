---
title: "Conversions d&#39;appel de fonction | Microsoft Docs"
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
  - "appels de fonction, conversions de type d'argument"
  - "appels de fonction, convertir"
  - "fonctions (C), conversions d'argument"
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversions d&#39;appel de fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type de conversion effectué sur les arguments dans un appel de fonction dépend de la présence d'un prototype de fonction \(déclaration anticipée\) avec les types d'argument déclarés pour la fonction appelée.  
  
 Si un prototype de fonction est présent et inclut des types d'argument déclarés, le compilateur effectue la vérification de type \(voir [Fonctions](../c-language/functions-c.md)\).  
  
 Si aucun prototype de fonction n'est présent, seules les conversions arithmétiques habituelles sont effectuées sur les arguments figurant dans l'appel de fonction.  Ces conversions sont effectuées indépendamment sur chaque argument figurant dans l'appel.  Cela signifie qu'une valeur **float** est convertie en valeur **double**, qu'une valeur `char` ou **short** est convertie en valeur `int` et qu'une valeur `unsigned char` ou **unsigned short** est convertie en valeur `unsigned int`.  
  
## Voir aussi  
 [Conversions de type](../c-language/type-conversions-c.md)