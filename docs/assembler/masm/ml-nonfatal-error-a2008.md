---
title: "ML Nonfatal Error A2008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2008"
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**erreur de syntaxe :**  
  
 Un jeton à la position actuelle a causé une erreur de syntaxe.  
  
 L'une des opérations suivantes a pu se produire :  
  
-   un préfixe de point a été ajouté à ou omis d'une directive.  
  
-   un mot réservé \(tel que **C** ou **SIZE**\) a été utilisé comme identificateur.  
  
-   Vous avez utilisé une instruction non disponibles avec la sélection de processeur actuel d'exploitation ou de coprocesseur.  
  
-   Un opérateur à l'exécution de comparaison \(tel qu' `==`\) est utilisé dans une instruction d'assembly conditionnel au lieu d'un opérateur de relation \(tel qu' [EQ](../../assembler/masm/operator-eq.md)\).  
  
-   Une instruction ou une directive a été attribuée trop peu d'opérandes.  
  
-   une directive obsolète a été utilisée.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)