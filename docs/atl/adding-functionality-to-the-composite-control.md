---
title: "Adding Functionality to the Composite Control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), événements"
  - "contrôles composites, gérer les événements"
  - "event handlers [C++], contrôles ActiveX"
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Adding Functionality to the Composite Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fois que vous avez inséré tous les contrôles nécessaires dans le contrôle composite, l'étape suivante implique l'ajout de nouvelles fonctionnalités.  Cette nouvelle fonctionnalité se range généralement en deux catégories :  
  
-   Interfaces supplémentaires de prise en charge et personnaliser le comportement de votre contrôle composite avec supplémentaire, caractéristiques spécifiques.  
  
-   Gestion des événements du contrôle ActiveX contenu \(ou des contrôles\).  
  
 Pour la fonction et la portée de cet article, le reste de cette section traite uniquement sur les événements de gestion des contrôles ActiveX.  
  
> [!NOTE]
>  Si vous devez gérer des messages de contrôles Windows, consultez l' [Implémentation d'une fenêtre](../atl/implementing-a-window.md) pour plus d'informations sur la gestion des messages dans ATL.  
  
 Après avoir inséré un contrôle ActiveX dans la ressource de boîte de dialogue, cliquez avec le bouton droit sur le contrôle et cliquez sur **Ajouter un gestionnaire d'événements**.  Sélectionnez l'événement à gérer et cliquez sur **Add and Edit**.  Le code de gestionnaire d'événements est ajouté au fichier .h du du contrôle.  
  
 Les points de connexion pour des contrôles ActiveX dans le contrôle composite sont automatiquement connectés et déconnectés via des appels à [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md).  
  
## Voir aussi  
 [Notions de base des contrôles composites](../atl/atl-composite-control-fundamentals.md)