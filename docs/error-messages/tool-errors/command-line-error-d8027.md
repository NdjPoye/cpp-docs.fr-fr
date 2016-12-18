---
title: "Erreur de ligne de commande&#160;D8027 | Microsoft Docs"
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
  - "D8027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8027"
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de ligne de commande&#160;D8027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'exécuter 'composant'  
  
 Le compilateur n'a pas pu exécuter le composant ou l'éditeur de liens du compilateur donné.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Mémoire insuffisante pour charger le composant.  Si NMAKE a appelé le compilateur, exécutez le compilateur en dehors du makefile.  
  
2.  Le système d'exploitation en cours n'a pas pu exécuter le composant.  Vérifiez que le composant pointe vers les fichiers exécutables adaptés à votre système d'exploitation.  
  
3.  Le composant a été endommagé.  Recopiez le composant à partir des disques de distribution à l'aide du programme d'installation.  
  
4.  Une option n'a pas été spécifiée correctement.  Par exemple :  
  
    ```  
    cl /B1 file1.c  
    ```