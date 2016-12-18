---
title: "Test des applications Internet | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déboguer (MFC), applications Web"
  - "déboguer les applications Web, test d'applications"
  - "Internet (déboguer et tester)"
  - "tester, applications Internet"
  - "applications Web, tester"
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Test des applications Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe des problèmes de test uniques sur Internet, notamment pour les applications qui s'exécutent sur un serveur Web.  Votre test initial sera probablement fait à l'aide d'un client mono\-utilisateur se connectant à un serveur de test.  Cela sera utile à des fins de débogage.  
  
 Vous souhaiterez également tester dans des conditions réelles : avec plusieurs clients connectés à sur les connexions haut débit ainsi que des lignes série à faible vitesse, y compris les connexions modem.  Il peut être difficile de simuler des conditions réelles, mais il est intéressant de passer un moment à la conception des scénarios possibles et de les exécuter.  Si possible, vous souhaiterez également utiliser des outils pour effectuer des tests de capacité et de contrainte.  Ccertaines classes les bogues, tels que les bogues d'horloge, sont difficiles à trouver et à reproduire.  
  
 Un des problèmes de la programmation Internet est sa visibilité.  De nombreux accès à votre site peuvent ralentir votre serveur.  Vous souhaiterez que votre serveur se dégrade gracieusement.  Vous voulez empêcher tout ce qui peut être néfaste pour l'ordinateur d'un utilisateur si votre application échoue \(par exemple, l'altération des données lors de l'écriture dans le Registre ou lors de l'écriture des cookies sur le client\).  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)