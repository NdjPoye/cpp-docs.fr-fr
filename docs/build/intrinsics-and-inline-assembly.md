---
title: "Assembly de fonctions intrins&#232;ques et inline | Microsoft Docs"
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
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Assembly de fonctions intrins&#232;ques et inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'une des contraintes du compilateur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] est de n'avoir aucune prise en charge d'assembleur inline.  Cela signifie que les fonctions qui ne peuvent pas être écrites en C ou C\+\+ doivent être écrites en tant que sous\-routine ou que fonctions intrinsèques prises en charge par le compilateur.  Certaines fonctions sont sensibles aux performances alors que d'autres ne le sont pas.  Les fonctions sensibles aux performances doivent être implémentées comme des fonctions intrinsèques.  
  
 Les fonctions intrinsèques prises en charge par le compilateur sont décrites dans la rubrique [Compilateurs intrinsèques](../intrinsics/compiler-intrinsics.md).  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)