---
title: "Conteneurs de contr&#244;les ActiveX&#160;: gestion d&#39;&#233;v&#233;nements &#224; partir d&#39;un contr&#244;le ActiveX | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), récepteurs d'événements"
  - "contrôles ActiveX (C++), événements"
  - "BEGIN_EVENTSINK_MAP (macro)"
  - "END_EVENTSINK_MAP (macro), utilisation"
  - "gestionnaires d'événements (C++), contrôles ActiveX"
  - "gestion des événements (C++), contrôles ActiveX"
  - "événements (C++), contrôles ActiveX"
  - "ON_EVENT (macro)"
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs de contr&#244;les ActiveX&#160;: gestion d&#39;&#233;v&#233;nements &#224; partir d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment utiliser la fenêtre Propriétés pour configurer les gestionnaires d'événements pour les contrôles ActiveX dans un conteneur de contrôles ActiveX.  Les gestionnaires d'événements sont utilisés pour recevoir des notifications \(du contrôle\) de certains événements et exécuter une action en réponse.  Cette notification est appelée "déclenchement" de l'événement.  
  
> [!NOTE]
>  Cet article utilise un projet basé sur les boîtes de dialogue des conteneurs de contrôles ActiveX nommé Container et un contrôle incorporé nommé Circ comme exemples dans les procédures et le code.  
  
 En utilisant le bouton d'événements dans la fenêtre de propriétés, vous pouvez créer une carte des événements qui peuvent se produire dans votre application conteneur de contrôles ActiveX.  Cette carte, appelée « table de récepteurs d'événements », est créée et gérée par Visual C\+\+ lorsque vous ajoutez des gestionnaires d'événements à la classe de conteneur de contrôle.  Chaque gestionnaire d'événements, implémenté avec une entrée de table d'événement, mappe un événement spécifique à une fonction membre du gestionnaire d'événements du conteneur.  Cette fonction du gestionnaire d'événements est appelée lorsque l'événement spécifié est déclenché par l'objet de contrôle ActiveX.  
  
 Pour plus d'informations sur les tables de récepteurs d'événements, consultez [Tables de récepteurs d'événements](../mfc/reference/event-sink-maps.md) dans *la référence de la bibliothèque de classes*.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a> Modifications du gestionnaire d'événements au projet  
 Lorsque vous utilisez la fenêtre Propriétés pour ajouter les gestionnaires d'événements, une table de récepteurs d'événements est déclarée et définie dans votre projet.  Les instructions suivantes sont ajoutées au fichier .cpp de contrôle la première fois qu'un gestionnaire d'événements est ajouté.  Ce code déclare une table de récepteurs d'événements pour la classe de la boîte de dialogue \(dans ce cas, `CContainerDlg`\) :  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 Lorsque vous utilisez la fenêtre Propriétés pour ajouter des événements, une entrée de table d'événement \(`ON_EVENT`\) est ajoutée à la table de récepteurs d'événements et une fonction gestionnaire d'événements est ajoutée au fichier d'implémentation du conteneur \(.CPP\).  
  
 L'exemple suivant déclare un gestionnaire d'événements, appelé `OnClickInCircCtrl`, pour l'événement **ClickIn** du contrôle de Circ :  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 En outre, le modèle suivant est ajouté au fichier de l'implémentation de la classe `CContainerDlg` \(.CPP\) pour la fonction membre du gestionnaire d'événements :  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 Pour plus d'informations sur les macros de récepteurs d'événements, consultez [Tables de récepteurs d'événements](../mfc/reference/event-sink-maps.md) dans *la référence de la bibliothèque de classes*.  
  
#### Pour créer une fonction gestionnaire d'événements  
  
1.  De l'Affichage de classes, sélectionnez la classe de la boîte de dialogue qui contient le contrôle ActiveX.  Pour cet exemple, utilisez `CContainerDlg`.  
  
2.  Dans la fenêtre Propriétés, cliquez sur le bouton **Événements**.  
  
3.  Dans la fenêtre Propriétés, sélectionnez l'ID du contrôle du contrôle ActiveX incorporé.  Utilisez `IDC_CIRCCTRL1` pour cet exemple.  
  
     La fenêtre Propriétés affiche une liste d'événements qui peuvent être déclenchés par le contrôle ActiveX incorporé.  Toute fonction membre apparaissant en gras a déjà une fonction gestionnaire affectée.  
  
4.  Sélectionnez l'événement que la classe de la boîte de dialogue doit gérer.  Pour cet exemple, sélectionnez **"Click"**.  
  
5.  Dans la liste déroulante à droite, selectionnez **\<Ajouter\> OnLButtonDown**.  
  
6.  Double\-cliquez sur la nouvelle fonction gestionnaire d'Affichage de classes pour accéder au code du gestionnaire d'événements dans le fichier d'implémentation \(.CPP\) de `CContainerDlg`.  
  
## Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)