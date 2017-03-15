---
title: "Avertissement du compilateur (niveau 4) C4513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4513"
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 4) C4513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : le destructeur n'a pas pu être généré  
  
 Le compilateur ne peut pas générer un destructeur par défaut pour la classe donnée ; aucun destructeur n'a été créé.  Le destructeur est dans une classe de base qui n'est pas accessible à la classe dérivée.  Si la classe de base a un destructeur privé, déclarez\-le public ou protégé.