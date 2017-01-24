---
title: "Erreur du compilateur C2030 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2030"
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un destructeur avec l'accessibilité 'protected private' ne peut pas être membre d'une classe déclarée 'sealed'  
  
 Une classe Windows Runtime déclarée comme `sealed` ne peut pas avoir un destructeur privé protégé.  Seuls des destructeurs virtuels publics et non virtuels privés sont autorisés sur les types sealed.  Pour plus d'informations, consultez [Classes et structures de référence](../Topic/Ref%20classes%20and%20structs%20\(C++-CX\).md).  
  
 Pour corriger cette erreur, modifiez l'accessibilité du destructeur.