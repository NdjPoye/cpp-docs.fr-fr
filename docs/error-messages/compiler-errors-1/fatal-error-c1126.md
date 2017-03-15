---
title: "Erreur irr&#233;cup&#233;rable C1126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1126"
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l'allocation automatique dépasse 'taille'  
  
 L'espace alloué aux variables locales d'une fonction \(plus une quantité limitée utilisée par le compilateur, telle que 20 octets supplémentaires pour les fonctions permutables\) dépasse la limite.  
  
 Pour remédier à cette erreur, utilisez `malloc` ou `new` pour allouer de grandes quantités de données.