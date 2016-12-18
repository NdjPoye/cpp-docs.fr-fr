---
title: "CMDIFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWnd class"
  - "MDI frame windows"
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDIFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une fenêtre frame d'interface multidocument \(MDI\) windows, ainsi que des membres pour gérer la fenêtre.  
  
## Syntaxe  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](../Topic/CMDIFrameWnd::CMDIFrameWnd.md)|Construit un `CMDIFrameWnd`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIFrameWnd::CreateClient](../Topic/CMDIFrameWnd::CreateClient.md)|Crée une fenêtre de **MDICLIENT** windows pour cet `CMDIFrameWnd`.  Appelé par la fonction membre d' `OnCreate` d' `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](../Topic/CMDIFrameWnd::CreateNewChild.md)|Crée une nouvelle fenêtre enfant.|  
|[CMDIFrameWnd::GetWindowMenuPopup](../Topic/CMDIFrameWnd::GetWindowMenuPopup.md)|Retourne le menu contextuel de la fenêtre.|  
|[CMDIFrameWnd::MDIActivate](../Topic/CMDIFrameWnd::MDIActivate.md)|Lance une fenêtre enfant MDI différente.|  
|[CMDIFrameWnd::MDICascade](../Topic/CMDIFrameWnd::MDICascade.md)|Réorganise toutes les fenêtres enfants dans un format affiche en cascade.|  
|[CMDIFrameWnd::MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md)|Récupère actuel \- la fenêtre enfant MDI active, avec une balise qui indique si l'enfant est agrandi.|  
|[CMDIFrameWnd::MDIIconArrange](../Topic/CMDIFrameWnd::MDIIconArrange.md)|Réorganise toutes les fenêtres enfants réduites de document.|  
|[CMDIFrameWnd::MDIMaximize](../Topic/CMDIFrameWnd::MDIMaximize.md)|Agrandit une fenêtre enfant MDI.|  
|[CMDIFrameWnd::MDINext](../Topic/CMDIFrameWnd::MDINext.md)|Active la fenêtre enfant immédiatement derrière actuel \- la fenêtre enfant active et définit actuel \- la fenêtre enfant active derrière toutes les autres fenêtres enfants.|  
|[CMDIFrameWnd::MDIPrev](../Topic/CMDIFrameWnd::MDIPrev.md)|Active la fenêtre enfant précédente et définit actuel \- la fenêtre enfant active immédiatement derrière elle.|  
|[CMDIFrameWnd::MDIRestore](../Topic/CMDIFrameWnd::MDIRestore.md)|Restaure une fenêtre enfant MDI de taille agrandie ou réduite.|  
|[CMDIFrameWnd::MDISetMenu](../Topic/CMDIFrameWnd::MDISetMenu.md)|Remplace le menu d'une fenêtre frame MDI, dans le menu contextuel de la fenêtre, ou des deux.|  
|[CMDIFrameWnd::MDITile](../Topic/CMDIFrameWnd::MDITile.md)|Réorganise toutes les fenêtres enfants dans un format en mosaïque.|  
  
## Notes  
 Pour créer une fenêtre frame MDI utile pour votre application, dérivez une classe d' `CMDIFrameWnd`.  Ajoutez des variables membres dans la classe dérivée au détail de données de mémoire à votre application.  Implémentez les fonctions membres gestionnaires de messages et une table des messages dans la classe dérivée pour spécifier ce qui se produit lorsque les messages sont dirigés vers la fenêtre.  
  
 Vous pouvez construire une fenêtre frame MDI en appelant la fonction membre de [Create](../Topic/CFrameWnd::Create.md) ou de [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) d' `CFrameWnd`.  
  
 Avant d'appeler **Créer** ou `LoadFrame`, vous devez construire l'objet de fenêtre frame sur le tas à l'aide de l'opérateur C\+\+ **nouveau** .  Avant de vous appelez **Créer** peut également stocker une classe de fenêtre avec la fonction globale d' [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) pour définir des styles d'icône et de classe pour le frame.  
  
 Utilisez la fonction membre de **Créer** pour passer des paramètres de la création du frame en tant qu'arguments immédiats.  
  
 `LoadFrame` requiert moins d'arguments que **Créer**, et extrait à la place la plupart de ses valeurs par défaut des ressources, y compris la légende du frame, l'icône, la table d'accélérateurs, et le menu.  Pour accéder au `LoadFrame`, toutes ces ressources doivent avoir le même ID de ressource \(par exemple, **IDR\_MAINFRAME**\).  
  
 Bien que **MDIFrameWnd** est dérivé d' `CFrameWnd`, une classe de fenêtre frame dérivée d' `CMDIFrameWnd` n'a pas besoin d'être déclarée avec `DECLARE_DYNCREATE`.  
  
 La classe d' `CMDIFrameWnd` hérite de nombreuses son implémentation par défaut d' `CFrameWnd`.  Pour une liste détaillée de ces fonctionnalités, consultez la description de classe de [CFrameWnd](../../mfc/reference/cframewnd-class.md) .  La classe d' `CMDIFrameWnd` a des fonctionnalités supplémentaires suivantes :  
  
-   Une fenêtre frame MDI gère la fenêtre de **MDICLIENT** , le repositionnant avec des barres de contrôles.  La fenêtre cliente MDI est le parent direct des fenêtres frame enfant MDI.  Les styles de fenêtre de **WS\_HSCROLL** et de **WS\_VSCROLL** spécifiés sur `CMDIFrameWnd` appliquent à la fenêtre cliente MDI plutôt que la fenêtre frame principale afin que l'utilisateur peut faire défiler la zone cliente MDI \(comme dans le gestionnaire de programme Windows, par exemple\).  
  
-   Une fenêtre frame MDI possède un menu par défaut qui est utilisé comme barre de menus lorsqu'il n'y a pas de fenêtre enfant MDI active.  Lorsqu'il existe un enfant MDI actif, la barre de menus de la fenêtre frame MDI est automatiquement remplacé par le menu de fenêtre enfant MDI.  
  
-   Une fenêtre frame MDI fonctionne conjointement avec la fenêtre enfant MDI actuelle, s'il y en a une.  Par exemple, les messages de commande sont délégués actuel \- à l'enfant MDI actif avant la fenêtre frame MDI.  
  
-   Une fenêtre frame MDI a les gestionnaires par défaut pour les commandes de menu Fenêtre standard suivantes :  
  
    -   **ID\_WINDOW\_TILE\_VERT**  
  
    -   **ID\_WINDOW\_TILE\_HORZ**  
  
    -   **ID\_WINDOW\_CASCADE**  
  
    -   **ID\_WINDOW\_ARRANGE**  
  
-   Une fenêtre frame MDI a également une implémentation d' **ID\_WINDOW\_NEW**, qui crée un nouveau frame et vue du document actif.  Une application peut substituer ces implémentations par défaut de commande pour personnaliser la gestion des fenêtres MDI.  
  
 N'utilisez pas l'opérateur C\+\+ **supprimer** pour détruire une fenêtre frame.  Utilisez plutôt `CWnd::DestroyWindow`.  L'implémentation d' `CFrameWnd` d' `PostNcDestroy` supprimera l'objet C\+\+ lorsque la fenêtre est détruite.  Lorsque l'utilisateur ferme la fenêtre frame, le gestionnaire par défaut d' `OnClose` appelle `DestroyWindow`.  
  
 Pour plus d'informations sur `CMDIFrameWnd`, consultez [fenêtres frames](../../mfc/frame-windows.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [MFC exemple MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC exemple SNAPVW](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)