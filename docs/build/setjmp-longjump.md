---
title: "setjmp/longjump | Microsoft Docs"
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
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setjmp/longjump
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous incluez setjmpex.h ou setjmp.h, les appels généraux à [setjmp](../c-runtime-library/reference/setjmp.md) ou [longjmp](../c-runtime-library/reference/longjmp.md) entraînent un déroulement qui appelle des destructeurs et enfin des appels.  Cela diffère de x86, où l'inclusion de setjmp.h n'entraîne aucun appel de clauses finally et de destructeurs.  
  
 Un appel à `setjmp` conserve le pointeur de pile actuel, les registres non volatils et les registres MxCsr.  Les appels à `longjmp` reviennent au site de l'appel `setjmp` le plus récent et rétablissent le pointeur de pile, les registres non volatils, ainsi que les registres MxCsr dans l'état préservé par le dernier appel de `setjmp`.  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)