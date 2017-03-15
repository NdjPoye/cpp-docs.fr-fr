---
title: "Taille de tableau la plus grande | Microsoft Docs"
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
ms.assetid: 4c782cf6-73f3-40b0-b306-229d22da4ee1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Taille de tableau la plus grande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3.3.4, 4.1.1** Le type d'entier requis pour conserver la taille maximale d'un tableau \(autrement dit, la taille **size\_t**\)  
  
 Le typedef `size_t` est `unsigned int` sur la plateforme x86 32 bits.  Sur les plateformes 64 bits, le typedef `size_t` est un **unsigned \_\_int64**.  
  
## Voir aussi  
 [Tableaux et pointeurs](../c-language/arrays-and-pointers.md)