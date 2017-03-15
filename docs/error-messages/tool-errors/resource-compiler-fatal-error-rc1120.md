---
title: "Erreur irr&#233;cup&#233;rable RC1120 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1120"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1120"
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable RC1120 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

mémoire insuffisante, octets nombre requis  
  
 Le compilateur de ressources ne dispose pas de suffisamment d'espace pour stocker les éléments dans le tas.  Ceci est généralement provoqué par un trop grand nombre de symboles.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Augmentez l'espace alloué au fichier d'échange Windows.  Pour plus d'informations sur l'augmentation de l'espace réservé au fichier d'échange, consultez les rubriques d'aide Windows se rapportant à la mémoire virtuelle.  
  
2.  Éliminez les fichiers include non requis, notamment les directives `#define` et les prototypes de fonction dont vous n'avez pas besoin.  
  
3.  Fractionnez le fichier en cours en deux ou plusieurs fichiers et compilez\-les séparément.  
  
4.  Supprimez les applications et gestionnaires exécutés sur le système qui utilisent une quantité importante de mémoire.