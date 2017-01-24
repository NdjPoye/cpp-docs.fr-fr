---
title: "Acc&#232;s non valide &#224; une union | Microsoft Docs"
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
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s non valide &#224; une union
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3.2.3** Un accès à un membre d'un objet d'union a lieu en utilisant un membre d'un type différent.  
  
 Si une union de deux types est déclarée et qu'une valeur est enregistrée, mais que l'union est accessible par l'autre type, les résultats ne sont pas fiables.  
  
 Par exemple, une union de type **float** et `int` est déclarée.  Une valeur de type **float** est stockée, mais le programme y accède ultérieurement en tant que `int`.  Dans ce cas, la valeur dépend du stockage interne des valeurs **float**.  La valeur entière n'est pas fiable.  
  
## Voir aussi  
 [Structures, unions, énumérations et champs de bits](../c-language/structures-unions-enumerations-and-bit-fields.md)