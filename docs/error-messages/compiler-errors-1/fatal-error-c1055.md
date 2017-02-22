---
title: "Erreur irr&#233;cup&#233;rable C1055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : clés insuffisantes  
  
 Le fichier source contient trop de symboles.  Le compilateur a manqué de clés de hachage pour la table de symboles.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Fractionnez le fichier source en fichiers plus petits.  
  
2.  Éliminez les fichiers d'en\-tête non nécessaires.  
  
3.  Réutilisez les variables temporaires et globales au lieu d'en créer de nouvelles.