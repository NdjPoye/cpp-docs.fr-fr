---
title: "Relations entre les objets MFC | Microsoft Docs"
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
  - "objets MFC (relations)"
  - "MFC, relations entre des objets clés"
  - "objets (C++), relations"
  - "relations, objets MFC"
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Relations entre les objets MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour aider à mettre le processus de création de documents\/vue dans la perspective, envisagez un programme en cours de exécution : un document, la fenêtre cadre utilisée pour contenir la vue, puis la vue associées au document.  
  
-   Un document conserve une liste des vues de ce document et un pointeur vers le modèle de document qui a créé le document.  
  
-   Une vue conserve un pointeur à son document et est un enfant de la fenêtre parente cadre.  
  
-   Une fenêtre cadre de document conserve un pointeur vers la vue active actuelle.  
  
-   Un modèle de document conserve une liste de les documents ouverts.  
  
-   L'application conserve une liste de ses modèles de document.  
  
-   Windows gère toutes les fenêtres actives elle peut envoyer des messages à celles\-ci.  
  
 Ces relations sont créées lors de la création de documents\/vue.  Le tableau suivant illustre les objets dans un programme en cours de exécution peuvent accéder à d'autres objets.  Tout objet peut obtenir un pointeur vers l'objet d'application en appelant la fonction globale [AfxGetApp](../Topic/AfxGetApp.md).  
  
### Accéder à d'autres objets dans votre application  
  
|à partir des objets|Comment accéder à d'autres objets|  
|-------------------------|---------------------------------------|  
|Document|Utilisez [GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md) et [GetNextView](../Topic/CDocument::GetNextView.md) pour accéder à la liste de la vue du document.<br /><br /> Appelez [GetDocTemplate](../Topic/CDocument::GetDocTemplate.md) pour obtenir le modèle de document.|  
|Vue|Appelez [GetDocument](../Topic/CView::GetDocument.md) pour obtenir le document.<br /><br /> Appelez [GetParentFrame](../Topic/CWnd::GetParentFrame.md) pour obtenir la fenêtre cadre.|  
|Fenêtres frame de document|Appelez [GetActiveView](../Topic/CFrameWnd::GetActiveView.md) pour obtenir la vue actuelle.<br /><br /> Appelez [GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md) pour obtenir le document associé à la vue actuelle.|  
|Fenêtre frame MDI|Appelez pour obtenir [MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md) actuellement actif [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)actif.|  
  
 En général, une fenêtre cadre d'une perspective, mais dans certains cas, comme dans les fenêtres de fractionnement, la même fenêtre cadre contient plusieurs vues.  La fenêtre cadre conserve un pointeur actuellement actif à la vue active ; le pointeur est mis à jour lorsqu'une vue est activée.  
  
> [!NOTE]
>  Pointeur vers la fenêtre principale cadre est stockée dans la variable membre [m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md) de l'objet d'application.  Un appel à `OnFileNew` de la substitution de la fonction membre de `InitInstance` d'`CWinApp` définit `m_pMainWnd` automatiquement.  Si vous n'appelez pas `OnFileNew`, vous devez définir la valeur de la variable dans `InitInstance` vous\-même. \(Les applications de composant \(serveur\) COM SDI peuvent ne pas définir la variable si \/Embedding est sur la ligne de commande.\) Notez que `m_pMainWnd` est maintenant un membre de la classe `CWinThread` plutôt que `CWinApp`.  
  
## Voir aussi  
 [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Création de modèle de document](../mfc/document-template-creation.md)   
 [Création d'un document\/d'une vue](../mfc/document-view-creation.md)   
 [Création de documents, fenêtres et vues](../mfc/creating-new-documents-windows-and-views.md)