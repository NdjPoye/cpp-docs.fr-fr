---
title: "Documents, vues et le Framework | Microsoft Docs"
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
  - "objets application (C++), relation avec les autres objets MFC"
  - "applications (MFC)"
  - "objets Document, par rapport autres objets MFC"
  - "modèles de document, objets de modèle"
  - "architecture document/vue, à propos de l'architecture document/vue (C++)"
  - "documents (C++)"
  - "MFC (C++), infrastructure de l'application"
  - "MFC (C++), documents"
  - "MFC (C++), vues"
  - "objets MFC (relations)"
  - "objets (C++), applications MFC"
  - "objets thread"
  - "objets de vue, relation avec les autres objets MFC"
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Documents, vues et le Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Au cœur de l'infrastructure MFC sont les concepts du document et de la vue.  Un document est un objet de données avec lequel l'utilisateur interagit dans une session d'édition.  Il est créé par la commande `New` ou **Open** dans le menu **File** et est généralement stocké dans un fichier. \(Les documents standard MFC, issus de la classe **CDocument**, sont différents des documents Active et des documents composés OLE.\) Une vue est un objet fenêtre via lequel l'utilisateur interagit avec un document.  
  
 Les objets principaux dans une application active sont :  
  
-   Le document ou les documents.  
  
     Votre classe de document \(dérivée de [CDocument](../mfc/reference/cdocument-class.md)\) spécifie les données d'application.  
  
     Si vous souhaitez des fonctionnalités OLE dans votre application, dérivez la classe de document de [COleDocument](../mfc/reference/coledocument-class.md) ou une de ses classes dérivées, selon le type de fonction dont vous avez besoin.  
  
-   La vue ou les vues.  
  
     La classe d'affichage \(dérivée de [CView](../mfc/reference/cview-class.md)\) est la "fenêtre" de l'utilisateur sur les données. La classe d'affichage contrôle comment l'utilisateur voit les données de votre document et interagit avec.  Dans certains cas, vous pouvez vouloir un document ayant plusieurs vues des données.  
  
     Si vous avez besoin de faire défiler, dérivez de [CScrollView](../mfc/reference/cscrollview-class.md).  Si votre vue a une interface utilisateur qui présentée dans une ressource modèle de la boîte de dialogue, dérivez de [CFormView](../mfc/reference/cformview-class.md).  Pour les données de texte simple, utilisez ou dérivez de [CEditView](../mfc/reference/ceditview-class.md).  Pour une application d'accès aux données de formulaire, par exemple un programme d'entrée de données, dérivez de [CRecordView](../mfc/reference/crecordview-class.md) \(pour ODBC\).  Également disponibles sont les classes [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), et [CRichEditView](../mfc/reference/cricheditview-class.md).  
  
-   Les fenêtres cadres  
  
     Les vues sont affichés dans "fenêtres cadres de document". Dans une application SDI, la fenêtre cadre de document correspond également à la fenêtre cadre « master » pour l'application.  Dans une application MDI, les fenêtres de document sont des fenêtres enfants affichées à l'intérieur d'une fenêtre cadre principale.  Votre classe dérivée de fenêtre cadre principale spécifie les styles et d'autres fonctionnalités des fenêtres cadres qui contiennent les vues.  Si vous devez personnaliser des fenêtres cadres, dérivez de [CFrameWnd](../mfc/reference/cframewnd-class.md) pour personnaliser la fenêtre cadre de document pour les applications SDI.  Dérivez de [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) pour personnaliser la fenêtre cadre principale pour les applications MDI.  Dérivez également une classe de [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) pour personnaliser chaque type distinct de fenêtre cadre de document MDI que votre application prend en charge.  
  
-   Le modèle de document ou les modèles  
  
     Un modèle de document orchestre la création des documents, des vues, et des fenêtres cadres.  Une classe en particulier de modèle de document, dérivée de la classe [CDocTemplate](../mfc/reference/cdoctemplate-class.md), crée et gère tous les documents ouverts d'un type.  Les applications qui prennent en charge plusieurs types de documents ont plusieurs modèles de document.  Utilisez la classe [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) pour les applications SDI, ou la classe [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) pour les applications MDI.  
  
-   L'objet application  
  
     La classe d'application \(dérivée de [CWinApp](../mfc/reference/cwinapp-class.md)\) contrôle les objets ci\-dessus et spécifie le comportement d'application tel que l'initialisation et la destruction.  Le seul et unique objet d'application de l'application crée et gère les modèles de document pour tout type de document pris en charge par l'application.  
  
-   Objets thread  
  
     Si votre application crée des threads séparés d'exécution \(par exemple, pour effectuer des calculs en arrière\-plan et utiliser les classes dérivées de [CWinThread](../mfc/reference/cwinthread-class.md).  [CWinApp](../mfc/reference/cwinapp-class.md) lui\-même est dérivé de `CWinThread` et représente le thread principal de l'exécution \(ou du processus principal\) dans votre application.  Vous pouvez également utiliser MFC dans les threads secondaires.  
  
 Dans une application active, ces objets répondent en coopération aux actions de l'utilisateur, liés par des commandes et d'autres messages.  Un objet d'application gère un ou plusieurs modèles de document.  Chaque modèle de document crée et gère un ou plusieurs documents \(selon que l'application est SDI ou MDI\).  L'utilisateur voit et manipule un document dans une vue contenue dans une fenêtre cadre.  L'illustration suivante montre les relations entre les objets pour une application SDI.  
  
 ![Objets dans une application SDI en cours d'exécution](../mfc/media/vc386v1.png "vc386V1")  
Objets dans une application SDI en cours d'exécution  
  
 Le reste de cette famille d'articles explique comment les outils d'infrastructure, l'Assistant Application MFC et les éditeurs de ressources, comment créer ces objets, leur fonctionnement, ainsi que comment les utiliser dans votre code.  Des documents, des vues, et des fenêtres cadres sont présentés plus en détail dans [Objets fenêtres](../mfc/window-objects.md) et [Documents\/Architecture des Vues](../mfc/document-view-architecture.md).  
  
## Voir aussi  
 [Utilisation des classes pour l'écriture d'applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)