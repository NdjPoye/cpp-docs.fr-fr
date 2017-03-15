---
title: "&#201;l&#233;ments de l&#39;interface | Microsoft Docs"
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
  - "architecture (C++), MFC Feature Pack"
  - "MFC Feature Pack, architecture"
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# &#201;l&#233;ments de l&#39;interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document décrit les éléments d'interface qui ont été introduits dans [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] SP1, et décrit les différences avec la version antérieure de la bibliothèque.  
  
 L'illustration suivante montre une application créée à l'aide de les éléments de l'interface.  
  
 ![Exemple d'application MFC Feature Pack](../mfc/media/mfc_featurepack.png "MFC\_FeaturePack")  
  
## Ancrage des fenêtres  
 La fonctionnalité d'ancrage de la fenêtre ressemble à l'extrémité d'affichage de l'interface utilisateur graphique de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise.  
  
## Les barres de contrôles sont désormais des volets  
 Les barres de contrôles sont maintenant appelé les volets et sont dérivées de [CBasePane Class](../mfc/reference/cbasepane-class.md).  Dans les versions antérieures de MFC, la classe de base des barres de contrôle est `CControlBar`.  
  
 La fenêtre principale cadre d'application est généralement représenté par [CFrameWndEx Class](../mfc/reference/cframewndex-class.md) ou [Classe CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md).  Le cadre principal est appelé *le site de l'ancre*.  Les volets peuvent prendre trois types de parents : un site de l'ancre, une barre de l'ancre, ou d'une fenêtre mini\-frame.  
  
 Il existe deux types de volets : non redimensionnable et redimensionnable.  Les volets redimensionnables, tels que les barres d'état et des barres d'outils, peuvent être redimensionnés en utilisant des séparateurs ou les curseurs.  Les volets redimensionnables peuvent constituer les conteneurs \(un volet peut être ancré à un autre volet, en créant un séparateur entre eux\).  Toutefois, les volets redimensionnables ne peuvent pas être joints \(ancré\) aux barres de l'ancre.  
  
 Si votre application utilise des volets non redimensionnables, les dérivez\- de [CPane Class](../mfc/reference/cpane-class.md).  Si votre application utilise des volets non redimensionnables, les dérivez\- de [CDockablePane Class](../mfc/reference/cdockablepane-class.md).  
  
## Ancrer le site  
 Le site de l'ancre \(ou cadre de la fenêtre principale\) détient tous les volets et windows mini\-frame dans une application.  Le site de l'ancre contient un membre d'[CDockingManager](../mfc/reference/cdockingmanager-class.md).  Ce membre contient une liste de tous les volets qui appartiennent au site de l'ancre.  La liste est triée afin que les volets créés aux sessions externes du site de l'ancre sont placés au début de la liste.  Lorsque l'infrastructure rafraîchit le site de l'ancre, la boucle sur cette liste et ajuste la mise en page de chaque volet pour inclure le rectangle englobant actuel du site de l'ancre.  Vous pouvez appeler `AdjustDockingLayout` ou `RecalcLayout` lorsque vous devez ajuster la disposition d'ancrage, et l'infrastructure redirige cet appel au gestionnaire d'ancrage.  
  
## Barres de l'ancre  
 Chaque fenêtre principale cadre peut placer *des barres de l'ancre* le long de les lignes de bordure.  Une barre de l'ancre est un volet qui appartient à [CDockSite Class](../mfc/reference/cdocksite-class.md).  Les barres de l'ancre peuvent recevoir les objets dérivés d'[CPane](../mfc/reference/cpane-class.md), tels que les barres d'outils.  Pour créer des barres de l'ancre lorsque la fenêtre principale cadre est initialisée, appelez `EnableDocking`.  Pour activer les barres de masquage automatique, appelez `EnableAutoHideBars`.  `EnableAutoHideBars` crée des objets d'[CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md), et les positionne en regard de chaque barre de l'ancre.  
  
 Chaque barre de l'ancre sont divisées en lignes de l'ancre.  Les lignes de l'ancre sont représentées par [CDockingPanesRow Class](../mfc/reference/cdockingpanesrow-class.md).  Chaque ligne de l'ancre contient une liste des barres d'outils.  Si un utilisateur accueille une barre d'outils ou déplace la barre d'outils d'une ligne vers un autre dans la même barre de l'ancre, l'infrastructure ou crée une ligne et redimensionne la barre de l'ancre en conséquence, il positionne la barre d'outils dans une ligne existante.  
  
## Windows mini\-frame  
 Un volet flottant réside dans une fenêtre mini\-frame.  Windows mini\-frame sont représentées par deux classes : [CMDITabInfo Class](../mfc/reference/cmditabinfo-class.md) \(qui peut contenir qu'un seul volet\) et [CMultiPaneFrameWnd Class](../mfc/reference/cmultipaneframewnd-class.md) \(qui peut contenir plusieurs volets.\)  Ajouter un appel dans le code à [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md).  Après un volet flotte, l'infrastructure crée automatiquement une fenêtre mini\-frame et cette fenêtre mini\-frame est le parent flottant du volet.  Lorsque le volet flottant l'accueille, l'infrastructure réinitialise son parent, le volet est flottant une barre de l'ancre \(pour les barres d'outils\) ou un site de l'ancre \(pour les volets redimensionnables\).  
  
## Diviseurs du volet  
 Les diviseurs du volet \(également appelés des curseurs ou des séparateurs\) sont représentés par [CPaneDivider Class](../mfc/reference/cpanedivider-class.md).  Lorsqu'un utilisateur accueille le volet, l'infrastructure crée des diviseurs du volet, que le volet est ancrée au site de l'ancre ou un autre volet.  Lorsqu'un volet l'accueille le site de l'ancre, le diviseur du volet est appelé *le diviseur par défaut du volet*.  Le diviseur par défaut du volet est responsable de la disposition de tous les volets d'ancrage du site de l'ancre.  Le gestionnaire de l'ancre contient une liste de diviseurs par défaut du volet, et une liste des volets.  Les gestionnaires de l'ancre sont responsables de la disposition de tous les volets d'ancrage.  
  
## Conteneurs  
 Tous les volets redimensionnables, une fois accueillis entre eux, sont conservés dans les conteneurs.  Les conteneurs sont représentés par [CPaneContainer Class](../mfc/reference/cpanecontainer-class.md).  Chaque conteneur possède des pointeurs vers le volet gauche, volet droit, sub conteneur gauche, sub conteneur correct, et le séparateur entre les parties gauche et de droite. \(*Les gauche* et à *droite* ne référence pas aux côtés physiques et identifient et les branches d'une arborescence.\) De cette manière nous pouvons générer une arborescence des volets et des séparateurs et donc pour obtenir les dispositions complexes les volets qui peuvent être redimensionnés ensemble.  La classe d'`CPaneContainer` conserve la hiérarchie des conteneurs ; elle contient également deux listes des volets et les curseurs qui résident dans cette arborescence.  Les gestionnaires de conteneur du volet sont généralement incorporés dans les curseurs par défaut et windows mini\-frame qui retiennent plusieurs volets.  
  
## Masquer automatiquement les barres de contrôle  
 Par défaut, chaque `CDockablePane` prend en charge les fonctionnalités de masquer automatiquement.  Lorsqu'un utilisateur clique sur le bouton de marque dans la légende d'`CDockablePane`, l'infrastructure bascule le volet pour masquer automatiquement le mode.  Pour gérer cliquez sur, l'infrastructure crée [CMFCAutoHideBar Class](../mfc/reference/cmfcautohidebar-class.md) et [CMFCAutoHideButton Class](../mfc/reference/cmfcautohidebutton-class.md) associés à l'objet d'`CMFCAutoHideBar`.  L'infrastructure met nouvel `CMFCAutoHideBar` sur [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md).  L'infrastructure joint également `CMFCAutoHideButton` dans la barre d'outils.  [CDockingManager Class](../mfc/reference/cdockingmanager-class.md) contient `CDockablePane`.  
  
## Barres de contrôle avec onglets et barres Outlook  
 [CMFCBaseTabCtrl Class](../mfc/reference/cmfcbasetabctrl-class.md) implémente les fonctionnalités de base d'une fenêtre avec onglets avec les onglets détachables.  Pour utiliser un objet d'`CMFCBaseTabCtrl`, initialisez [Classe CBaseTabbedPane](../mfc/reference/cbasetabbedpane-class.md) dans votre application.  `CBaseTabbedPane` est dérivé d'`CDockablePane` et contient un pointeur vers un objet d'`CMFCBaseTabCtrl`.  \+`CBaseTabbedPane` permet aux utilisateurs d'ancrage et redimensionner les barres de contrôle avec onglets.  Utilisation [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) de créer dynamiquement les barres de contrôles qui sont accueillies et tabulées.  
  
 Le contrôle de la barre Outlook est également selon les barres à onglets.  L'élément [CMFCOutlookBar, Classe](../mfc/reference/cmfcoutlookbar-class.md) est dérivé de `CBaseTabbedPane`.  Pour plus d'informations sur l'utilisation de cette commande, consultez [CMFCOutlookBar, Classe](../mfc/reference/cmfcoutlookbar-class.md).  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)