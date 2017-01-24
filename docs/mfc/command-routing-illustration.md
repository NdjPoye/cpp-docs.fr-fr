---
title: "Illustration du routage des commandes | Microsoft Docs"
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
  - "gestion des commandes, router des commandes"
  - "routage des commandes, OnCmdMsg (gestionnaire)"
  - "MFC, routage des commandes"
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Illustration du routage des commandes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour illustrer cela, considérez un message de commande d'un élément de menu Effacer tout dans le menu Edition d'une application MDI.  Supposons que la fonction gestionnaire de cette commande se trouve être une méthode de la classe de documents de l'application.  Voici comment cette commande atteint son gestionnaire lorsque l'utilisateur choisit l'élément de menu :  
  
1.  La fenêtre cadre principale reçoit le message de commande en premier.  
  
2.  La fenêtre cadre principale MDI donne à la fenêtre enfant MDI active couramment une occasion de gérer la commande.  
  
3.  Le routage standard d'une fenêtre cadre enfant MDI permet à la vue une chance d'accès à la commande avant de vérifier sa propre table des messages.  
  
4.  La vue vérifie sa propre table des messages d'abord et, ne trouvant pas de responsable, fait suivre la commande à son document associé.  
  
5.  Le document active la table des messages et trouve un responsable.  Cette méthode du document est appelée et le transit s'arrête.  
  
 Si le document n'a aucun responsable, il acheminerait ensuite la commande à son modèle de document.  La commande reviendrait à la vue puis dans la fenêtre cadre.  Enfin, la fenêtre cadre vérifierait sa table des messages.  Si cette vérification a également échoué, la commande est acheminée vers la fenêtre cadre principale puis à l'objet d'application — la destination finale des commandes non prises en charge.  
  
## Voir aussi  
 [Méthode d'appel d'un gestionnaire par le Framework](../mfc/how-the-framework-calls-a-handler.md)