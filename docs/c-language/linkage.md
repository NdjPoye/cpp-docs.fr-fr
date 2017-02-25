---
title: "Liaison | Microsoft Docs"
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
  - "liaison (C++)"
  - "liaison (C++), noms et portée des identificateurs"
ms.assetid: 986ee549-2d6c-487a-9e3b-a1f643bc5bdc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Liaison
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les noms d'identificateurs peuvent faire référence à des identificateurs dans différentes portées.  Un identificateur déclaré dans différentes portées ou dans la même portée plusieurs fois peut être créé pour faire référence au même identificateur ou fonction par un processus appelé « liaison ». La liaison détermine les parties du programme où un identificateur peut être référencé \(sa « visibilité »\).  Il existe trois types de liaison : [interne](../c-language/internal-linkage.md), [externe](../c-language/external-linkage.md), et [aucune liaison](../c-language/no-linkage.md).  
  
## Voir aussi  
 [Utilisation d'extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)