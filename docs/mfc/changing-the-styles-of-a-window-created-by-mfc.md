---
title: "Modification des styles d&#39;une fen&#234;tre cr&#233;&#233;e par MFC | Microsoft Docs"
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
  - "CFrameWnd (classe), styles de fenêtres"
  - "fenêtres enfants, styles"
  - "CMainFrame (classe)"
  - "CMDIChildWnd (classe), changer les styles de fenêtres"
  - "CREATESTRUCT (macro)"
  - "style de fenêtre par défaut"
  - "valeurs par défaut (C++), style de fenêtre"
  - "MDI (C++), styles de fenêtres"
  - "MFC (C++), fenêtres"
  - "style d'interface multidocument"
  - "PreCreateWindow (méthode), changer les styles de fenêtres"
  - "PreCreateWindow (méthode), styles de fenêtres"
  - "interface monodocument, changer les attributs de fenêtre"
  - "interface monodocument, style"
  - "styles, fenêtres"
  - "styles de fenêtres (C++)"
  - "fenêtres (C++), MFC"
  - "WS_OVERLAPPEDWINDOW (macro)"
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Modification des styles d&#39;une fen&#234;tre cr&#233;&#233;e par MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans cette version de la fonction `WinMain`, MFC contient plusieurs classes de fenêtre standard.  Étant donné que vous ne modifiez normalement pas la `WinMain`de MFC, cette fonction ne vous permet pas de modifier les styles de fenêtre par défaut de MFC.  Cet article explique comment modifier les styles d'une telle classe de fenêtre pré\-enregistrée dans une application existante.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Modifier les styles dans une nouvelle application MFC  
 Si vous utilisez Visual C\+\+ 2.0 ou une version ultérieure, il est possible de modifier les styles d'affichage par défaut dans l'Assistant d'application lorsque vous créez votre application.  Dans la page de fonctionnalités de l'interface utilisateur de l'Assistant Application, modifiez les styles de la fenêtre principale cadre et fenêtres enfants MDI.  Pour l'un des types de fenêtre, spécifiez son épaisseur de cadre \(épais ou amincir\) et les éléments suivants :  
  
-   Si la fenêtre a les contrôles Minimiser ou Maximiser.  
  
-   Si la fenêtre apparaît initialement réduite, agrandie, ou ni l'un ni l'autre.  
  
 Pour les fenêtres cadre principales, vous pouvez également spécifier si la fenêtre possède un menu système.  Pour les fenêtres enfants MDI, vous pouvez spécifier si la fenêtre prend en charge les volets de séparateur.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a> Modifier les styles d'une application existante  
 Si vous modifiez les attributs de fenêtre dans une application existante, suivez les instructions du reste de l'article à la place.  
  
 Pour modifier les attributs par défaut d'affichage utilisés par une application du framework créée avec l'Assistant d'Application, substituez la fenêtre de fonction virtuelle membre [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).  `PreCreateWindow` permet à une application d'accéder au processus de conception normalement géré en interne par la classe [CDocTemplate](../mfc/reference/cdoctemplate-class.md).  L'infrastructure appelle `PreCreateWindow` juste avant de créer la fenêtre.  En modifiant sa structure [CREATESTRUCT](../mfc/reference/createstruct-structure.md) passée à `PreCreateWindow`, votre application peut modifier les attributs utilisés pour créer la fenêtre.  Par exemple, pour vous assurer qu'une fenêtre n'utilise pas de légende, utilisez l'opération de bits suivantes :  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/CPP/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 L'exemple d'application de [CTRLBARS](../top/visual-cpp-samples.md) illustre cette technique pour modifier les attributs de fenêtre.  Selon ce que votre application modifie dans `PreCreateWindow`, il peut être nécessaire d'appeler l'implémentation de la classe de la fonction.  
  
 Les paragraphes suivants couvrent le cas de SDI et du [Cas MDI](#_core_the_mdi_case).  
  
##  <a name="_core_the_sdi_case"></a> Le cas de SDI  
 Dans une application d'interface monodocument \(SDI\), le style d'affichage par défaut dans l'infrastructure est une combinaison des styles de **WS\_OVERLAPPEDWINDOW** et de **FWS\_ADDTOTITLE**.  **FWS\_ADDTOTITLE** est un style spécifique à MFC qui demande au framework d'ajouter le titre du document dans la légende de la fenêtre.  Pour modifier les attributs de fenêtre dans une application de SDI, substituez la fonction `PreCreateWindow` dans votre classe dérivée `CFrameWnd` \(que l'Application nomme `CMainFrame`\).  Par exemple :  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/CPP/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 Ce code crée une fenêtre cadre principale sans boutons d'agrandissement et réduction et sans bordure dimensionnable.  La fenêtre est initialement centrée sur l'écran.  
  
##  <a name="_core_the_mdi_case"></a> Le cas de MDI  
 Un peu plus de travail est requis pour modifier le style d'affichage de la fenêtre enfant dans une application d'interface multidocument \(MDI\).  Par défaut, une application MDI créée avec l'Assistant d'Application utilise la classe par défaut [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) définie dans MFC.  Pour modifier le style d'affichage de la fenêtre enfant MDI, vous devez dériver une nouvelle classe de `CMDIChildWnd` et remplacer toutes les références à `CMDIChildWnd` dans votre projet par des références à la nouvelle classe.  Très probablement, la seule référence à `CMDIChildWnd` dans l'application se trouve dans la fonction membre `InitInstance` de votre application.  
  
 Le style d'affichage par défaut utilisé dans une application MDI est une combinaison des styles de **WS\_CHILD**, de **WS\_OVERLAPPEDWINDOW**, et de **FWS\_ADDTOTITLE**.  Pour modifier les attributs d'affichage des fenêtres enfants d'une application MDI, substituez la fonction [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) dans votre classe dérivée de `CMDIChildWnd`.  Par exemple :  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/CPP/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 Ce code crée des fenêtres enfants MDI sans bouton Agrandir.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [styles de fenêtres](../mfc/reference/window-styles.md)  
  
-   [Styles des cadres des fenêtres](../mfc/frame-window-styles-cpp.md)  
  
-   [\<caps:sentence id\="tgt44" sentenceid\="26254917059da4aba50f886a6c5db931" class\="tgtSentence"\>Styles de fenêtre\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## Voir aussi  
 [Styles de fenêtre frame](../mfc/frame-window-styles-cpp.md)