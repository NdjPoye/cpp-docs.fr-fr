---
title: "Types multidocuments, vues et fen&#234;tres frame | Microsoft Docs"
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
  - "statiques, fenêtres fractionnées"
  - "vues multiples"
  - "types multidocuments"
  - "vues multiples, fenêtres frame"
  - "classes de document, multiples"
  - "documents (C++), types multiples de"
  - "fractionnées dynamiques, fenêtres"
  - "dynamiques, fenêtres fractionnées"
  - "fenêtres (C++), fractionnées dynamiques"
  - "fenêtres (C++), fractionnées statiques"
  - "fenêtres frame multiples"
  - "fenêtres fractionnées, statiques"
ms.assetid: c6b9e4e0-7c9c-45f1-a804-aeac39c9a128
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Types multidocuments, vues et fen&#234;tres frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La relation standard entre un document, sa vue et sa fenêtre frame est décrite dans [Création d’un document\/d’une vue](../mfc/document-view-creation.md). De nombreuses applications prennent en charge un type de document unique \(éventuellement plusieurs documents ouverts de ce type\) avec une seule vue du document et une seule fenêtre frame par document. Mais certaines applications peuvent avoir besoin de modifier une ou plusieurs de ces valeurs par défaut.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Types multidocuments](#_core_multiple_document_types)  
  
-   [Vues multiples](#_core_multiple_views)  
  
-   [Fenêtres frame multiples](#_core_multiple_frame_windows)  
  
-   [Fenêtres fractionnées](#_core_splitter_windows)  
  
##  <a name="_core_multiple_document_types"></a> Types multidocuments  
 L’Assistant Application MFC crée une classe de document unique pour vous. Cependant, dans certains cas, vous pouvez être amené à prendre en charge plusieurs types de document. Par exemple, votre application peut nécessiter des feuilles de calcul et des graphiques. Chaque type de document est représenté par sa propre classe de document et probablement par sa propre classe de vue. Quand l’utilisateur sélectionne la commande Fichier Nouveau, l’infrastructure affiche une boîte de dialogue qui répertorie les types de documents pris en charge. Elle crée ensuite un document du type sélectionné par l’utilisateur. Chaque type de document est géré par son propre objet modèle de document.  
  
 Pour créer des classes de document supplémentaires, consultez [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md). Choisissez [CDocument](../mfc/reference/cdocument-class.md) comme Type de classe à partir duquel dériver et indiquez les informations de document nécessaires. Implémentez ensuite les données de la nouvelle classe.  
  
 Pour que l’infrastructure reconnaisse votre classe de document supplémentaire, vous devez ajouter un deuxième appel à [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) dans la substitution [InitInstance](../Topic/CWinApp::InitInstance.md) de la classe d’application. Pour plus d’informations, consultez [Modèles de document](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
##  <a name="_core_multiple_views"></a> Vues multiples  
 Bon nombre de documents ne nécessitent qu’une seule vue, mais il est possible de prendre en charge plusieurs vues d’un même document. Pour vous aider à implémenter plusieurs vues, un objet document conserve une liste de ses vues, fournit des fonctions membres pour ajouter et supprimer des vues, et fournit la fonction membre [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) pour prévenir plusieurs vues de la modification des données du document.  
  
 MFC prend en charge trois interfaces utilisateur courantes nécessitant des vues multiples du même document. Ces modèles sont les suivants :  
  
-   Objets de vue de la même classe, chacun dans une fenêtre frame de document MDI distincte.  
  
     Vous pouvez prendre en charge la création d’une deuxième fenêtre frame d’un document. L’utilisateur peut choisir une commande Nouvelle fenêtre pour ouvrir une deuxième fenêtre frame avec une vue du même document, puis utiliser les deux fenêtres frame pour afficher simultanément différentes parties du document. Pour prendre en charge la commande Nouvelle fenêtre du menu Fenêtre pour les applications MDI, l’infrastructure duplique la fenêtre frame et la vue initiales jointes au document.  
  
-   Objets de vue de la même classe dans la même fenêtre frame de document.  
  
     Les fenêtres fractionnées divisent l’espace de vue d’une fenêtre de document unique en plusieurs vues distinctes du document. L’infrastructure crée plusieurs objets de vue de la même classe de vue. Pour plus d’informations, consultez [Fenêtres fractionnées](#_core_splitter_windows).  
  
-   Objets de vue de différentes classes dans une même fenêtre frame.  
  
     Dans ce modèle, une variante de la fenêtre fractionnée, plusieurs vues partagent une même fenêtre frame. Les vues sont construites à partir de différentes classes, chaque vue présentant le même document d’une façon différente. Par exemple, une vue peut afficher un document de traitement de texte en mode normal tandis qu’une autre vue peut l’afficher en mode plan. Un contrôle splitter permet à l’utilisateur d’ajuster les tailles relatives des vues.  
  
 La figure suivante, divisée en plusieurs parties \(a, b et c\), présente les trois modèles d’interface utilisateur dans l’ordre indiqué ci\-dessus.  
  
 ![Interfaces utilisateur à plusieurs affichages](../mfc/media/vc37a71.png "vc37A71")  
Interfaces utilisateur à plusieurs vues  
  
 Pour proposer ces modèles, l’infrastructure implémente la commande Nouvelle fenêtre et fournit la classe [CSplitterWnd](../mfc/reference/csplitterwnd-class.md), comme indiqué dans [Fenêtres fractionnées](#_core_splitter_windows). Vous pouvez implémenter d’autres modèles en utilisant ceux\-ci comme point de départ. Pour obtenir des exemples de programmes qui illustrent différentes configurations de vues, de fenêtres frame et de fenêtres fractionnées, consultez [Exemples MFC](../top/visual-cpp-samples.md).  
  
 Pour plus d’informations sur `UpdateAllViews`, consultez la classe [CView](../mfc/reference/cview-class.md) dans *Référence MFC* et [Exemple Scribble](../top/visual-cpp-samples.md).  
  
##  <a name="_core_multiple_frame_windows"></a> Fenêtres frame multiples  
 Vous pouvez utiliser la commande Nouvelle fenêtre du menu Fenêtre pour que les applications MDI créent une deuxième fenêtre frame du même document. Pour plus d’informations, consultez le premier modèle dans la figure [Interfaces utilisateur à plusieurs vues](#_core_multiple.2d.view_user_interfaces).  
  
##  <a name="_core_splitter_windows"></a> Fenêtres fractionnées  
 Dans une fenêtre fractionnée, la fenêtre est, ou peut être, divisée en deux volets ou plus qu’il est possible de faire défiler. Un contrôle splitter \(ou « curseur de fractionnement »\) dans le frame de fenêtre à côté des barres de défilement permet à l’utilisateur d’ajuster les tailles relatives des volets. Chaque volet est une vue du même document. Dans les fenêtres fractionnées « dynamiques », les vues sont de la même classe, comme le montre la partie b de la figure [Interfaces utilisateur à plusieurs vues](#_core_multiple.2d.view_user_interfaces). Dans les fenêtres fractionnées « statiques », les vues peuvent être de différentes classes. La classe [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) prend en charge les fenêtres fractionnées des deux types.  
  
 Les fenêtres fractionnées dynamiques, avec des vues de la même classe, permettent aux utilisateurs de fractionner une fenêtre en plusieurs volets à volonté et de faire défiler les différents volets pour afficher différentes parties du document. L’utilisateur peut également supprimer le fractionnement de la fenêtre pour supprimer les vues supplémentaires. Les fenêtres fractionnées ajoutées à l’[exemple Scribble](../top/visual-cpp-samples.md) illustrent ce propos. Cette rubrique décrit la technique de création de fenêtres fractionnées dynamiques. Une fenêtre fractionnée dynamique est illustrée dans la partie b de la figure [Interfaces utilisateur à plusieurs vues](#_core_multiple.2d.view_user_interfaces).  
  
 Les fenêtres fractionnées statiques, avec des vues de différentes classes, commencent avec la fenêtre fractionnée en plusieurs volets, chacune avec un objectif différent. Par exemple, dans l’éditeur de bitmaps Visual C\+\+, la fenêtre image affiche deux volets côte à côte. Le volet gauche affiche une image grandeur réelle de la bitmap. Le volet de droite affiche une image avec zoomée ou agrandie de la même bitmap. Les volets sont séparés par une « barre de fractionnement » que l’utilisateur peut faire glisser pour modifier les tailles relatives des volets. Une fenêtre fractionnée statique est illustrée dans la partie c de la figure [Interfaces utilisateur à plusieurs vues](#_core_multiple.2d.view_user_interfaces).  
  
 Pour plus d’informations, consultez la classe [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) dans *Référence MFC* et [Exemples MFC](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)