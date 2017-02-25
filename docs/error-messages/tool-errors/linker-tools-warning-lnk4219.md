---
title: "Avertissement des outils &#201;diteur de liens LNK4219 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4219"
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement des outils &#201;diteur de liens LNK4219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dépassement de la correction type\_de\_correction.Cible 'nom du symbole cible' hors limites, insertion du thunk  
  
 L'éditeur de liens a inséré un thunk dans une situation où l'adresse ou le décalage n'a pas pu tenir dans l'instruction donnée parce que le symbole cible est trop loin de l'emplacement de l'instruction.  
  
 Vous pouvez essayer de réorganiser l'image \(par exemple en utilisant l'option [\/ORDER](../../build/reference/order-put-functions-in-order.md)\) pour éviter le niveau supplémentaire d'indirection.