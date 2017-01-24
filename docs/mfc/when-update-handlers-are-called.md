---
title: "Quand les gestionnaires de mise &#224; jour sont-ils appel&#233;s&#160;? | Microsoft Docs"
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
  - "routage des commandes, commandes de mise à jour"
  - "routage des commandes, gestionnaires de mise à jour"
  - "désactiver les éléments de menu"
  - "désactiver les boutons de barre d'outils"
  - "éléments de menu, activer"
  - "menus (C++), initialiser"
  - "menus (C++), mettre à jour au fur et à mesure des changements de contexte"
  - "boutons de barre d'outils (C++), activer"
  - "contrôles de barre d'outils (MFC), mis à jour au cours de la méthode OnIdle"
  - "barres d'outils (C++), mettre à jour"
  - "gestionnaires de mise à jour"
  - "gestionnaires de mise à jour, appeler"
  - "mettre à jour des objets de l'interface utilisateur"
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Quand les gestionnaires de mise &#224; jour sont-ils appel&#233;s&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supposons que l'utilisateur clique dans le menu Fichier, ce qui génère un message `WM_INITMENUPOPUP`.  Le mécanisme de mise à jour du framework met à jour collectivement tous les éléments du menu Fichier avant que le mense se déroule afin que l'utilisateur puisse le voir.  
  
 Pour cela, le framework route des commandes de mise à jour des commandes pour tous les éléments du menu dans le menu contextuel sur le routage des commandes standard.  Les cibles de la commande du routage ont la possibilité de mettre à jour tous les éléments de menu en faisant correspondre la commande de mise à jour avec une entrée de la table des messages appropriée \(au format `ON_UPDATE_COMMAND_UI`\) et en appelant la fonction « gestionnaire de mise à jour ».  Par conséquent, pour un menu avec six éléments de menu, six commandes de mise à jour sont envoyées.  Si le conseiller de mise à jour existe pour l'ID de commande de l'élément de menu, elle est appelée pour effectuer la mise à jour.  Sinon, l'infrastructure vérifie l'existence d'un gestionnaire pour cet ID de commande et active ou désactive l'élément de menu comme il convient.  
  
 Si le frameworkne trouve pas d'entrée `ON_UPDATE_COMMAND_UI` pendant le routage des commandes, il active automatiquement l'objet d'interface utilisateur s'il y a une entrée `ON_COMMAND` quelque part avec le même ID de commande.  Sinon, elle désactive l'objet d'interface utilisateur.  Par conséquent, pour vous assurer qu'un objet d'interface utilisateur est activé, fournissez un gestionnaire pour que la commande que l'objet génère ou fournissez un gestionnaire de mise à jour pour celle\-ci.  Consultez l'exemple dans la rubrique [Objets d'interface utilisateur et ID de commande](../mfc/user-interface-objects-and-command-ids.md).  
  
 Il est possible de désactiver par la désactivation défaut des objets interface utilisateur.  Pour plus d'informations, consultez la fonction membre de [m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md) de la classe `CFrameWnd` dans *le guide MFC*.  
  
 L'initialisation de menu est automatique dans le framework, survenant lorsque l'application reçoit un message `WM_INITMENUPOPUP`.  Lors de la boucle inactive, lle framework recherche le routage des commandes pour les gestionnaires de mise à jour du bouton de la même façon que pour les menus.  
  
## Voir aussi  
 [Comment : mettre à jour des objets d'interface utilisateur](../mfc/how-to-update-user-interface-objects.md)