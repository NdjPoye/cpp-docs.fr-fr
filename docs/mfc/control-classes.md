---
title: "Classes de contr&#244;le | Microsoft Docs"
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
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boutons, classes de contrôle MFC"
  - "classes de contrôle"
  - "classes de contrôle, MFC"
  - "contrôles (C++), classes de contrôle MFC"
  - "contrôles (MFC)"
  - "zones de liste, classes de contrôle MFC"
  - "contrôles d'affichage statique"
  - "texte, contrôles pour l'entrée"
  - "entrée d'utilisateur, classes de contrôle MFC"
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes de contrôle encapsulent une grande variété de contrôles Windows standard allant des contrôles statiques de texte aux contrôles d'arborescence.  En outre, MFC fournit quelques nouveaux contrôles, y compris les boutons de bitmap et de barres de contrôle.  
  
 Les commandes dont le nom de classe se terminent en « **Ctrl** » étaient nouvelles dans la version 3.51 de Windows 95 et Windows NT.  
  
## contrôles d'affichage statique  
 [CStatic](../mfc/reference/cstatic-class.md)  
 Une fenêtre d'affichage statique.  Les contrôles statiques sont utilisés pour étiqueter, emboîter, ou séparer d'autres contrôles dans une boîte de dialogue ou dans une fenêtre.  Ils peuvent également afficher des images graphiques au lieu de texte ou d'une boîte.  
  
## Contrôles de texte  
 [CEdit](../mfc/reference/cedit-class.md)  
 Unz fenêtre de contrôle de texte modifiable.  Les contrôles d'édition sont utilisés pour accepter l'entrée textuelle de l'utilisateur.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 Prend en charge une zone d'édition pour manipuler une adresse de \(IP\) \(Internet protocol\).  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 Un contrôle dans lequel l'utilisateur peut entrer et modifier du texte.  Contrairement au contrôle inclus dans `CEdit`, un contrôle RichEdit prend en charge le caractère et la mise en forme de paragraphe et les objets OLE.  
  
## Contrôles qui représentent des nombres  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 Un contrôle qui contient un curseur, que l'utilisateur déplace pour sélectionner une valeur ou un ensemble de valeurs.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 Une paire de boutons fléchés sur lesquels les utilisateurs peuvent cliquer pour incrémenter ou décrémenter une valeur  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 Affiche un rectangle qui est rempli progressivement de gauche à droite pour afficher la progression d'une opération.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 Une fenêtre de contrôle de barre de défilement  La classe fournit la fonctionnalités de barre de défilement, pour une utilisation en tant que contrôle dans une boîte de dialogue ou une fenêtre, par le biais desquelles l'utilisateur peut spécifier une position dans une plage.  
  
## Boutons  
 [CButton](../mfc/reference/cbutton-class.md)  
 Une fenêtre de contrôle bouton  La classe fournit une interface de programmation d'un bouton de commande, de case à cocher, ou de case d'option dans la boîte de dialogue ou dans une fenêtre.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 Un bouton de bitmap plutôt qu'une légende de texte.  
  
## Listes  
 [CListBox](../mfc/reference/clistbox-class.md)  
 Une fenêtre de contrôle de zone de liste déroulante  Une zone de liste affiche une liste d'éléments que l'utilisateur peut afficher et sélectionner.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Fournit ma fonctionnalités d'une zone de liste Windows, permet à l'utilisateur de déplacer des éléments de boîte de liste, tels que des noms de fichiers et les chaînes de caractères, dans la zone de liste.  Les zones de liste avec cette fonction sont utiles pour obtenir une liste d'éléments dans un ordre différent de l'ordre alphabétique, notamment inclure des chemins ou des fichiers dans un projet.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 Une fenêtre de contrôle de zone de liste déroulante  Une zone de liste déroulante comprend un contrôle d'édition et une zone de liste.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 Étend le contrôle de zone de liste déroulante en fournissant la prise en charge des listes d'images.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 Affiche une liste d'éléments avec des cases à cocher, que l'utilisateur peut activer ou désactiver, en regard de chaque élément.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 affiche une collection d'éléments, chacune comprenant une icône et un nom, d'une manière semblable au volet droit de l'Explorateur de fichiers.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 Affiche une liste hiérarchique d'icônes arrangée de manière similaire au volet gauche de l'Explorateur de fichiers.  
  
## barres d'outils et barres d'état ;  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Fournit les fonctionnalités du contrôle commun de barre d'outils Windows.  La plupart des programmes de MFC utilisent [CToolBar](../mfc/reference/ctoolbar-class.md) au lieu de cette classe.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Une fenêtre horizontale, généralement divisée en volets, où une application peut afficher les informations d'état.  La plupart des programmes de MFC utilisent [CStatusBar](../mfc/reference/cstatusbar-class.md) au lieu de cette classe.  
  
## Divers contrôles  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 Affiche un clip vidéo simple.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Une petite fenêtre indépendante qui contient une seule ligne de texte qui décrit l'objectif d'un outil dans une application.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 Prend en charge un contrôle d'édition étendue, ou un contrôle de l'interface simple de calendrier, qui permet à un utilisateur de choisir une date spécifique ou une valeur d'heure.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 Affiche des titres ou étiquettes pour des colonnes.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 Prend en charge un contrôle d'interface simple de calendrier qui permet à un utilisateur de sélectionner une date.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 Un contrôle avec des onglets sur lesquels l'utilisateur peut cliquer, analogues aux diviseurs d'un livre.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 Permet à l'utilisateur de créer une combinaison de touches d'accès rapide, sur lesquelles l'utilisateur peut appuyer pour exécuter une action rapidement.  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 Affiche le texte balisé et lance des applications appropriées lorsque l'utilisateur clique sur le lien incorporé.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 Fournit les fonctionnalités du contrôle ActiveX WebBrowser dans une fenêtre MFC.  
  
## Classes liées  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Fournit les fonctionnalités de la liste d'images Windows.  Les listes d'images sont utilisées avec des contrôles de liste et des contrôles d'arborescence.  Elles peuvent également être utilisées pour stocker et archiver un ensemble de bitmap de tailles identiques.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 La classe de base pour toutes les vues associées aux contrôles Windows.  Les vues basées sur des contrôles sont décrites ci\-dessous.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Une vue qui contient un contrôle d'édition Windows standard.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Une vue qui contient un contrôle rich edit Windows.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Une vue qui contient un contrôle de liste Windows.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Une vue qui contient un contrôle d'arborescence Windows.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)