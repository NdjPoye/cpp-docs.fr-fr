---
title: "TN025&#160;: cr&#233;ation de document, vue et frame | Microsoft Docs"
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
  - "vc.creation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "documents, vue et cadre (création)"
  - "TN025"
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN025&#160;: cr&#233;ation de document, vue et frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit des problèmes de conception et de propriété pour des WinApps, des DocTemplates, des documents, des cadres et des vues.  
  
## WinApp  
 Il y a un objet `CWinApp` dans le système.  
  
 Il est statiquement construit et initialisé par l'implémentation interne de l'infrastructure `WinMain`.  Vous devez dériver de `CWinApp` pour faire quelque chose utile \(exception : les DLL d'extension ne doivent pas avoir une instance de `CWinApp` — l'initialisation est créée dans `DllMain` à la place\).  
  
 L'objet `CWinApp` possède une liste de modèles de document \( `CPtrList`\).  Il existe un ou plusieurs modèles de document par application.  Les DocTemplates sont généralement chargés à partir du fichier de ressources \(autrement dit, un tableau de chaînes\) dans `CWinApp::InitInstance`.  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);  
AddDocTemplate(pTemplate);  
```  
  
 L'objet `CWinApp` possède toutes les fenêtres cadres dans l'application.  La principale fenêtre cadre de l'application doit figurer dans **CWinApp::m\_pMainWnd**; en général vous définissez `m_pMainWnd` dans l'implémentation de `InitInstance` si vous n'avez pas autorisé AppWizard à le faire pour vous.  Pour l'interface monodocument \(SDI\) il s'agit d'un `CFrameWnd` qui sert de cadre d'application principale ainsi que le seul cadre de fenêtre de document.  Pour l'interface à plusieurs documents \(MDI\) il s'agit d'un cadre MDI cadre \(classe `CMDIFrameWnd`\) qui sert de principal fenêtre de cadre d'application content tous les enfants `CFrameWnd`s.  Chaque fenêtre enfant est de la classe `CMDIChildWnd` \(dérivé de `CFrameWnd`\) et sert en tant qu'une des potentiellement nombreuses fenêtres de cadre de document.  
  
## DocTemplates  
 `CDocTemplate` est le créateur et le gestionnaire de documents.  Il possède les documents qu'il crée.  Si votre application utilise une approche basée sur les ressources décrite ci\-dessous, il n'aura pas besoin de le déduire de `CDocTemplate`.  
  
 Pour une application de SDI, la classe `CSingleDocTemplate` suit un document ouvert.  Pour une application MDI, la classe `CMultiDocTemplate` conserve une liste \( `CPtrList`\) de tous les documents ouverts actuellement créés à partir de ce modèle.  `CDocTemplate::AddDocument` et `CDocTemplate::RemoveDocument` fournissent des fonctions membres virtuelles pour ajouter ou supprimer un document du modèle.  `CDocTemplate` est un ami de **CDocument** afin que nous puissions définir le pointeur protégé de restauration de **CDocument::m\_pDocTemplate** pour pointer vers le modèle de doc qui a créé le document.  
  
 `CWinApp` gère l'implémentation par défaut de `OnFileOpen`, qui à son tour interrogera tous les modèles de doc.  L'implémentation inclut déjà la recherche les documents ouverts et la détermination du format à ouvrir pour de nouveaux documents.  
  
 `CDocTemplate` gère la liaison d'interface utilisateur des documents et des cadres.  
  
 `CDocTemplate` conserve le nombre de documents sans nom.  
  
## CDocument  
 Un **CDocument** appartient à `CDocTemplate`.  
  
 Les documents ont une liste de vues actuellement ouverts \(dérivées de `CView`\) qui affichent le document \( `CPtrList`\).  
  
 Les documents ne créent pas\/ne détruisent pas les vues, mais ils sont joints entre eux lorsqu'ils sont créés.  Lorsqu'un document est fermé \(autrement dit, par Fichier\/Fermer\), toutes les vues jointes sont fermées.  Lorsque la dernière vue sur un document est fermée \(autrement dit, Fenêtre\/Fermer\) le document est fermé.  
  
 Les interfaces `CDocument::AddView`, `RemoveView` sont utilisées pour contenir la liste de la vue.  **CDocument** est un ami de `CView` nous puissions définir le pointeur arrière de **CView::m\_pDocument**.  
  
## CFrameWnd  
 `CFrameWnd` \(également appelé cadre\) joue le rôle de MFC 1,0, mais désormais la classe `CFrameWnd` est conçue pour être utilisé dans de nombreux cas sans dériver une nouvelle classe.  Les classes dérivées `CMDIFrameWnd` et `CMDIChildWnd` sont également améliorées donc bon nombre de commandes standard sont déjà implémentées.  
  
 Le `CFrameWnd` est chargé de créer des fenêtres dans la zone client du cadre.  Normalement il existe une fenêtre principale remplissant la zone client du cadre.  
  
 Pour une fenêtre de cadre MDI, la zone client est remplie avec le contrôle de MDICLIENT qui est à son tour le parent de toutes les fenêtres enfants cadre MDI.  Pour une fenêtre cadre SDI ou une fenêtre cadre enfants MDI, la zone client est généralement remplie par un objet fenêtre `CView` déduit.  Dans le cas de `CSplitterWnd`, la zone client de la vue est remplie par l'objet fenêtre `CSplitterWnd`, et la `CView`\- objets fenêtre déduits \(un par panneau séparé\) sont créés en tant que fenêtres enfants de `CSplitterWnd`.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)