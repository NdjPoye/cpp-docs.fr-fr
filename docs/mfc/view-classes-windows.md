---
title: "Classes d&#39;affichage (Windows) | Microsoft Docs"
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
  - "vc.classes.view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vues d'enregistrements et de formulaires"
  - "classes de fenêtres fractionnées"
  - "classes vues, Windows"
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes d&#39;affichage (Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CView` et ses classes dérivées sont des fenêtres enfants qui représentent la zone client d'une fenêtre cadre.  Les vues affichent des données et acceptent des entrées pour un document.  
  
 Une classe d'affichage est associée à une classe de document et une classe cadre de fenêtre en utilisant un objet modèle de document.  
  
 [CView](../mfc/reference/cview-class.md)  
 La classe de base pour les vues spécifiques à l'application des données d'un document.  Les vues affichent des données et acceptent des entrées utilisateur pour modifier ou sélectionner des données.  Dériver la classe d'affichage ou des classes de `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 La classe de base pour les vues avec des capacités de défilement.  Dériver la classe de `CScrollView` pour le défilement automatique.  
  
## vues d'enregistrements et de formulaires  
 Les vues formulaire sont aussi des vues de défilement.  Elles sont basées sur un modèle de boîte de dialogue.  
  
 Les vues d'enregistrements sont dérivées des vues formulaire.  Outre le modèle de boîte de dialogue, elles possèdent également une connexion à une base de données.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Une zone de défilement dont la structure est définie dans un modèle de boîte de dialogue.  Dérivez une classe de `CFormView` pour implémenter une interface utilisateur basée sur un modèle de la boîte de dialogue.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Fournit un mode formulaire directement connectée à un objet recordset d'accès aux données \(DAO\).  Comme tous les modes formulaire, un `CDaoRecordView` est basé sur le modèle de la boîte de dialogue.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Fournit un mode formulaire directement connectée à un objet recordset ODBC \(Open Database Connectivity\).  Comme tous les modes formulaire, un `CRecordView` est basé sur le modèle de la boîte de dialogue.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 Une vue formulaire qui fournit des fonctionnalités de la plateforme d'édition HTML WebBrowser.  
  
## vues de contrôle  
 Les affichages de contrôle affichent un contrôle en tant que vue.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 La classe de base pour toutes les vues associées aux contrôles Windows.  Les vues basées sur des contrôles sont décrites ci\-dessous.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Une vue qui contient un contrôle d'édition Windows standard \(consultez [CEdit](../mfc/reference/cedit-class.md)\).  Les contrôles d'édition prennent en charge des capcités pour l'édition, la recherche, le remplacement, et le défilement de texte.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Une vue qui contient un contrôle RichEdit Windows \(consultez [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Outre les fonctions d'un contrôle d'édition, les contrôles RichEdits prennent en charge les polices, des couleurs, la mise en forme de paragraphe, et les objets OLE incorporés.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Une vue qui contient un contrôle de liste Windows \(consultez [CListCtrl](../mfc/reference/clistctrl-class.md)\).  Un contrôle de liste affiche une collection d'éléments, chacune comprenant une icône et un nom, d'une manière semblable au volet droit de l'Explorateur de fichiers.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Une vue qui contient un contrôle d'arborescence Windows \(consultez [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  Un contrôle d'arborescence affiche une liste hiérarchique d'icônes arrangée de manière similaire au volet gauche de l'Explorateur de fichiers.  
  
## Classes liées  
 `CSplitterWnd` vous permet d'avoir plusieurs perspectives dans une fenêtre cadre.  `CPrintDialog` et `CPrintInfo` prennent en charge la fonctionnalité d'impression et d'aperçu avant impression des vues.  `CRichEditDoc` et `CRichEditCntrItem` sont utilisés avec `CRichEditView` pour implémenter les capacités de conteneur OLE.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 Une fenêtre que l'utilisateur peut se diviser en plusieurs volets.  Ces volets peuvent être redimensionnables par l'utilisateur ou de taille fixe.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Affiche une boîte de dialogue standard pour imprimer un fichier.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Une structure qui contient des informations sur un travail d'impression ou un aperçu avant impression.  Utilisé par l'architecture d'impression de `CView`.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Maintient la liste d'éléments client OLE qui sont dans un `CRichEditView`.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Fournit l'accès côté client OLE à un élément stocké dans `CRichEditView`.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)