---
title: "Erreur irr&#233;cup&#233;rable RC1002 du compilateur de ressources  | Microsoft Docs"
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
  - "RC1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1002"
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable RC1002 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace du tas insuffisant  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Augmentez l'espace alloué au fichier d'échange Windows.  Pour plus d'informations sur l'augmentation de l'espace réservé au fichier d'échange, consultez les rubriques d'aide Windows se rapportant à la mémoire virtuelle.  
  
2.  Fractionnez le fichier en cours en fichiers moins volumineux et compilez\-les séparément.  
  
3.  Supprimez les autres applications ou gestionnaires exécutés sur le système.