---
title: "CMDIChildWnd Class | Microsoft Docs"
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
  - "CMDIChildWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres enfants, CMDIChildWnd class"
  - "CMDIChildWnd class"
  - "MDI (C++), fenêtres enfants"
  - "windows [C++], MDI"
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDIChildWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une fenêtre enfant d'interface multidocument \(MDI\) windows, ainsi que des membres pour gérer la fenêtre.  
  
## Syntaxe  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](../Topic/CMDIChildWnd::CMDIChildWnd.md)|Construit un objet `CMDIChildWnd`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMDIChildWnd::Create](../Topic/CMDIChildWnd::Create.md)|Crée la fenêtre enfant MDI windows associé à l'objet d' `CMDIChildWnd` .|  
|[CMDIChildWnd::GetMDIFrame](../Topic/CMDIChildWnd::GetMDIFrame.md)|Retourne le frame parent MDI de la fenêtre cliente MDI.|  
|[CMDIChildWnd::MDIActivate](../Topic/CMDIChildWnd::MDIActivate.md)|Lance cette fenêtre enfant MDI.|  
|[CMDIChildWnd::MDIDestroy](../Topic/CMDIChildWnd::MDIDestroy.md)|Perd cette fenêtre enfant MDI.|  
|[CMDIChildWnd::MDIMaximize](../Topic/CMDIChildWnd::MDIMaximize.md)|Agrandit cette fenêtre enfant MDI.|  
|[CMDIChildWnd::MDIRestore](../Topic/CMDIChildWnd::MDIRestore.md)|Restaure cette fenêtre enfant MDI de taille agrandie ou réduite.|  
|[CMDIChildWnd::SetHandles](../Topic/CMDIChildWnd::SetHandles.md)|Définit les handles pour les ressources de menu et en accélérateur.|  
  
## Notes  
 Recherche d'une fenêtre MDI enfant à l'instar d'une fenêtre frame classique, sauf que la fenêtre enfant MDI s'affiche dans une fenêtre frame MDI plutôt que sur le Bureau.  Une fenêtre MDI enfant n'a pas de barre de menus de sa propre, mais partage à la place le menu de la fenêtre frame MDI.  L'infrastructure modifie automatiquement le menu de frame MDI pour représenter actuel \- la fenêtre enfant MDI active.  
  
 Pour créer une fenêtre enfant MDI utile pour votre application, dérivez une classe d' `CMDIChildWnd`.  Ajoutez des variables membres dans la classe dérivée au détail de données de mémoire à votre application.  Implémentez les fonctions membres gestionnaires de messages et une table des messages dans la classe dérivée pour spécifier ce qui se produit lorsque les messages sont dirigés vers la fenêtre.  
  
 Il existe trois façons de construire une fenêtre enfant MDI :  
  
-   Construisez\- directement à l'aide de la **Créer**.  
  
-   Construisez\- directement à l'aide de la `LoadFrame`.  
  
-   Construisez\- indirectement la via un modèle de document.  
  
 Avant d'appeler **Créer** ou `LoadFrame`, vous devez construire l'objet de fenêtre frame sur le tas à l'aide de l'opérateur C\+\+ **nouveau** .  Avant de vous appelez **Créer** peut également stocker une classe de fenêtre avec la fonction globale d' [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) pour définir des styles d'icône et de classe pour le frame.  
  
 Utilisez la fonction membre de **Créer** pour passer des paramètres de la création du frame en tant qu'arguments immédiats.  
  
 `LoadFrame` requiert moins d'arguments que **Créer**, et extrait à la place la plupart de ses valeurs par défaut des ressources, y compris la légende du frame, l'icône, la table d'accélérateurs, et le menu.  Pour être accessibles par `LoadFrame`, toutes ces ressources doivent avoir le même ID de ressource \(par exemple, **IDR\_MAINFRAME**\).  
  
 Lorsqu'un objet d' `CMDIChildWnd` contient des vues et des documents, ils sont créés indirectement par l'infrastructure plutôt que directement par le programmeur.  l'objet d' `CDocTemplate` orchestre la création du frame, la création des vues contenantes, et la connexion des vues au document approprié.  Les paramètres du constructeur d' `CDocTemplate` spécifient `CRuntimeClass` les trois classes impliquées \(document, frame, et affichage\).  Un objet d' `CRuntimeClass` est utilisé par l'infrastructure pour créer dynamiquement de nouveaux frames une fois spécifié par l'utilisateur \(par exemple, en utilisant la nouvelle commande de fichier ou une commande de fenêtre MDI de la nouvelle\).  
  
 Une classe de fenêtre frame dérivée d' `CMDIChildWnd` doit être déclarée avec `DECLARE_DYNCREATE` pour que le mécanisme ci\-dessus d' `RUNTIME_CLASS` fonctionne correctement.  
  
 La classe d' `CMDIChildWnd` hérite de nombreuses son implémentation par défaut d' `CFrameWnd`.  Pour une liste détaillée de ces fonctionnalités consultez la description de classe de [CFrameWnd](../../mfc/reference/cframewnd-class.md) .  La classe d' `CMDIChildWnd` a des fonctionnalités supplémentaires suivantes :  
  
-   Conjointement avec la classe d' `CMultiDocTemplate` , plusieurs objets d' `CMDIChildWnd` du même modèle de document partagent le même menu, enregistrer les ressources système Windows.  
  
-   Actuel \- le menu de fenêtre enfant MDI actif remplace complètement le menu de fenêtre frame MDI, et la légende du actuel \- la fenêtre enfant MDI active est ajoutée à la légende de la fenêtre frame MDI.  Pour d'autres exemples de fonctions de fenêtre enfant MDI qui sont implémentées conjointement avec une fenêtre frame MDI, consultez la description de classe d' `CMDIFrameWnd` .  
  
 N'utilisez pas l'opérateur C\+\+ **supprimer** pour détruire une fenêtre frame.  Utilisez plutôt `CWnd::DestroyWindow`.  L'implémentation d' `CFrameWnd` d' `PostNcDestroy` supprimera l'objet C\+\+ lorsque la fenêtre est détruite.  Lorsque l'utilisateur ferme la fenêtre frame, le gestionnaire par défaut d' `OnClose` appelle `DestroyWindow`.  
  
 Pour plus d'informations sur `CMDIChildWnd`, consultez [fenêtres frames](../../mfc/frame-windows.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [MFC exemple MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC exemple SNAPVW](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)