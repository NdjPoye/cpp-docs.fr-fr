---
title: "Erreur irr&#233;cup&#233;rable C1054 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1054"
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : initialiseurs imbriqués trop profondément  
  
 Le code dépasse la limite d'imbrication des initialiseurs \(10\-15 niveaux, selon la combinaison de types initialisés\).  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Simplifiez les types de données initialisés pour réduire l'imbrication.  
  
2.  Initialisez les variables dans des instructions séparées après la déclaration.