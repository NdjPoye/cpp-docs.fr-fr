---
title: "operator IMAGEREL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operator IMAGEREL"
  - "IMAGEREL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator IMAGEREL"
  - "IMAGEREL operator"
ms.assetid: 5b5ea425-36f0-467c-9262-62c484b7fdb4
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator IMAGEREL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne l'offset relatif d'image d' `expression`.  
  
## Syntaxe  
  
```  
IMAGEREL expression  
```  
  
## Notes  
 La valeur résultante est souvent indiquée comme RVA ou adresse virtuelle associée.  
  
 IMAGEREL est uniquement disponible avec l'émission d'objet COFF.  
  
## Voir aussi  
 [Operators Reference](../../assembler/masm/operators-reference.md)