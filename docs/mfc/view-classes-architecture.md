---
title: "Classes d&#39;affichage (Architecture) | Microsoft Docs"
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
  - "vues de contrôle"
  - "vues d'enregistrements et de formulaires"
  - "classes vues"
  - "classes vues, architecture"
ms.assetid: 8894579a-1436-441e-b985-83711061e495
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes d&#39;affichage (Architecture)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CView` et ses classes dérivées sont des fenêtres enfants qui représentent la zone client d'une fenêtre cadre.  Les vues affichent des données et acceptent des entrées pour un document.  
  
 Une classe d'affichage est associée à une classe de document et une classe cadre de fenêtre en utilisant un objet modèle de document.  
  
 [CView](../mfc/reference/cview-class.md)  
 La classe de base pour les vues spécifiques à l'application des données d'un document.  Les vues affichent des données et acceptent des entrées utilisateur pour modifier ou sélectionner des données.  Dériver votre \(vos\) classe\(s\) de vue de `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 La classe de base pour les vues avec des capacités de défilement.  Dériver votre classe de vue de `CScrollView` pour le défilement automatique.  
  
## Vues d'enregistrements et de formulaires  
 Les vues de formulaire sont aussi des vues de défilement.  Elles sont basées sur un modèle de boîte de dialogue.  
  
 Les vues d'enregistrements sont dérivées des vues de formulaire.  Outre le modèle de boîte de dialogue, elles possèdent également une connection à une base de données.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Une zone de défilement dont la structure est définie dans un modèle de boîte de dialogue.  Dérivez une classe de `CFormView` pour implémenter une interface utilisateur basée sur un modèle de la boîte de dialogue.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Fournit un mode formulaire directement connecté à un objet recordset d'accès aux données \(DAO\).  Comme tous les modes formulaire, un `CDaoRecordView` est basé sur le modèle de la boîte de dialogue.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 Prend en charge un contrôle de navigation web dans une application.  Le contrôle prend en charge le DHTML de MFC.  
  
 [COlEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 Prend en charge des bases de données croisées OLE MFC pour des vues de formulaire.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Fournit une vue formulaire directement connectée à un objet recordset ODBC \(Open Database Connectivity\).  Comme toutes les vues de formulaire, un `CRecordView` est basé sur le modèle de la boîte de dialogue.  
  
## Vues de contrôle  
 Les affichages de contrôle affichent un contrôle en tant que vue.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 La classe de base pour toutes les vues associées aux contrôles Windows.  Les vues basées sur des contrôles sont décrites ci\-dessous.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Une vue qui contient un contrôle d'édition Windows standard \(consultez [CEdit](../mfc/reference/cedit-class.md)\).  Les contrôles d'édition prennent en charge des capacités pour l'édition, la recherche, le remplacement, et le défilement de texte.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Une vue qui contient un contrôle RichEdit Windows \(consultez [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Outre les fonctions d'un contrôle d'édition, les contrôles RichEdits prennent en charge les polices, les couleurs, la mise en forme de paragraphe, et les objets OLE incorporés.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Une vue qui contient un contrôle de liste Windows \(consultez [CListCtrl](../mfc/reference/clistctrl-class.md)\).  Un contrôle de liste affiche les icônes et les chaînes d'une manière semblable au volet droit de l'Explorateur de fichiers.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Une vue qui contient un contrôle d'arborescence Windows \(consultez [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\).  Icônes et chaînes d'affichage d'un contrôle d'arborescence ordonnés de façon hiérarchique d'une manière semblable au volet gauche de l'Explorateur de fichiers.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)