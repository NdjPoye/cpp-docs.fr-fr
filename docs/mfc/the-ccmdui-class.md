---
title: "CCmdUI, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdUI (classe), mise à jour de menu"
  - "barres d'outils (C++), mettre à jour"
  - "gestionnaires de mise à jour"
  - "mettre à jour des objets de l'interface utilisateur"
  - "objets de l'interface utilisateur, mettre à jour"
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCmdUI, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'il achemine une commande de mise à jour à son responsable, l'infrastructure passe au gestionnaire un pointeur vers un objet d' `CCmdUI` \(ou vers un objet de `CCmdUI`\- classe dérivée\).  Cet objet représente l'élément de menu ou le bouton de la barre d'outils ou un autre objet d'interface utilisateur qui a généré la commande.  Le conseiller de mise à jour appelle les fonctions membres de la structure d' `CCmdUI` par le pointeur pour mettre à jour l'objet d'interface utilisateur.  Par exemple, voici un gestionnaire de mise à jour l'élément de menu Tout Effacer:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/CPP/the-ccmdui-class_1.cpp)]  
  
 Ce gestionnaire appelle la fonction membre d' **Activer** d'un objet avec l'accès à l'élément de menu.  **Activer** rend l'élément disponible pour utilisation.  
  
## Voir aussi  
 [Comment : mettre à jour des objets d'interface utilisateur](../mfc/how-to-update-user-interface-objects.md)