---
title: "Op&#233;rations de bits sign&#233;s | Microsoft Docs"
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
  - "opérations de bits"
  - "opérations de bits signés"
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rations de bits sign&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3** Résultats des opérations au niveau du bit sur les entiers signés  
  
 Les opérations au niveau du bit sur les entiers signés fonctionnent de la même façon que les opérations au niveau du bit sur les entiers non signés.  Par exemple, les valeurs `–16 & 99` peuvent être exprimées au format binaire sous la forme  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Le résultat de l'opération de bits AND est 96.  
  
## Voir aussi  
 [Entiers](../c-language/integers.md)