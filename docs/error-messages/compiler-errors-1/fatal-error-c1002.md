---
title: "Erreur irr&#233;cup&#233;rable C1002 | Microsoft Docs"
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
  - "C1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1002"
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace du tas insuffisant pour le compilateur lors de la deuxième passe  
  
 Le compilateur a manqué d'espace de mémoire dynamique à la deuxième passe, sans doute parce qu'un programme contient trop de symboles ou d'expressions complexes.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Fractionnez le fichier source en fichiers source plus petits.  
  
2.  Fractionnez les expressions en sous\-expressions plus petites.  
  
3.  Supprimez les autres programmes ou pilotes qui occupent de la mémoire.