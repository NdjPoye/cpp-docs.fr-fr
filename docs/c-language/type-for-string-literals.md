---
title: "Type pour les litt&#233;raux de cha&#238;ne | Microsoft Docs"
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
  - "littéraux de chaîne, type"
  - "types (C), littéraux de chaîne"
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type pour les litt&#233;raux de cha&#238;ne
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les littéraux de chaîne ont un tableau de type `char` \(autrement dit, **char\[ \]**\). \(Les chaînes à caractères larges ont un tableau de type `wchar_t` \(autrement dit, **wchar\_t\[ \]**\).\) Cela signifie qu'une chaîne est un tableau avec des éléments de type `char`.  Le nombre d'éléments du tableau est égal au nombre de caractères dans la chaîne plus un pour le caractère null de fin.  
  
## Voir aussi  
 [Littéraux de chaîne C](../c-language/c-string-literals.md)