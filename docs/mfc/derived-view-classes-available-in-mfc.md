---
title: "Classes d&#39;affichage d&#233;riv&#233;es disponibles dans MFC | Microsoft Docs"
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
  - "classes (C++), dérivés"
  - "CView (classe), classes dérivées de"
  - "classes dérivées, classes vues"
  - "classes vues, dérivés"
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes d&#39;affichage d&#233;riv&#233;es disponibles dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant répertorie les classes d'affichage de MFC et leurs relations les uns par rapport aux autres.  Les fonctions de votre classe d'affichage dépendent de la classe d'affichage de MFC de laquelle elles dérivent.  
  
### Classes de vue  
  
|Classe|Description|  
|------------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|Classe de base de toutes les vues.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Classe de base d' `CTreeView`, d' `CListView`, d' `CEditView`, et d' `CRichEditView`.  Ces classes vous permettent d'utiliser l'architecture documents\/Vue avec les contrôles communs Windows indiquées.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Une vue simple basée sur le contrôle de la zone d'édition Windows.  Permet d'écrire et modifier le texte et peut être utilisé comme base pour une simple application de l'éditeur de texte.  Voir aussi `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Une vue qui contient un objet de [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md).  Cette classe est analogue à `CEditView`, mais contrairement à `CEditView`, `CRichEditView` gère les textes formatés.|  
|[CListView](../mfc/reference/clistview-class.md)|Une vue qui contient un objet de [CListCtrl](../mfc/reference/clistctrl-class.md).|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Une vue qui contient un objet de [CTreeCtrl](../mfc/reference/ctreectrl-class.md), pour les vues qui ressemblent à l'explorateur de solutions dans Visual C\+\+.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Classe de base d' `CFormView`, d' `CRecordView`, d' `CDaoRecordView`, et d' .  Implémente en faisant défiler le contenu de la vue.|  
|[CFormView](../mfc/reference/cformview-class.md)|Un mode formulaire, une vue qui contient des contrôles.  Une application basée sur les formulaires fournit un ou plusieurs de ces interfaces du formulaire.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Une vue de navigateur Web avec laquelle l'utilisateur de l'application peut parcourir les sites sur le Web, ainsi que fichiers dans le système de fichiers local et sur un réseau.  La vue navigateur Web peut également fonctionner comme conteneur de documents actifs.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|Une vue qui affiche des enregistrements de base de données ODBC dans les contrôles.  Si vous activez la prise en charge ODBC dans votre projet, la classe de base de la vue est `CRecordView`.  La vue est connectée à un objet de `CRowset`.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Une vue qui affiche des enregistrements de base de données DAO dans les contrôles.  Si vous activez la prise en charge DAO dans votre projet, la classe de base de la vue est `CDaoRecordView`.  La vue est connectée à un objet de `CDaoRecordset`.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Une vue qui affiche des enregistrements de DB OLE dans des contrôles.  Si vous activez la prise en charge des DB OLE dans votre projet, la classe de base de la vue est `COleDBRecordView`.  La vue est connectée à un objet de `CRowset`.|  
  
> [!NOTE]
>  Concernant la version 4.0 de MFC, `CEditView` est dérivé de `CCtrlView`.  
  
 Pour utiliser ces classes dans votre application, dérivez les classes de vue de l'application de ces derniers.  Pour plus d'informations, consultez [Vues de défilement et mise à l'échelle](../mfc/scrolling-and-scaling-views.md).  Pour plus d'informations sur les classes de base de données, consultez [Vue d'ensemble : Programmation de base de données](../data/data-access-programming-mfc-atl.md).  
  
## Voir aussi  
 [Utilisation de vues](../mfc/using-views.md)