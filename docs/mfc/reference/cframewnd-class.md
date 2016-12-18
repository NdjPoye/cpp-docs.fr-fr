---
title: "CFrameWnd Class | Microsoft Docs"
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
  - "CFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWnd class"
  - "frame window classes, classe de base"
  - "frame windows, créer"
  - "interface monodocument, frame windows"
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une interface monodocument fenêtre frame chevauchée ou contextuelle de \(SDI\) windows, ainsi que des membres pour gérer la fenêtre.  
  
## Syntaxe  
  
```  
class CFrameWnd : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFrameWnd::CFrameWnd](../Topic/CFrameWnd::CFrameWnd.md)|Construit un objet `CFrameWnd`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFrameWnd::ActivateFrame](../Topic/CFrameWnd::ActivateFrame.md)|Rend le frame visible et accessible à l'utilisateur.|  
|[CFrameWnd::BeginModalState](../Topic/CFrameWnd::BeginModalState.md)|Définit la fenêtre frame à modale.|  
|[CFrameWnd::Create](../Topic/CFrameWnd::Create.md)|Appelez pour créer et initialiser la fenêtre frame de fenêtre associé à l'objet d' `CFrameWnd` .|  
|[CFrameWnd::CreateView](../Topic/CFrameWnd::CreateView.md)|Crée une vue dans un frame qui n'est pas dérivé d' `CView`.|  
|[CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md)|Ancre une barre de contrôles.|  
|[CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md)|Permet une barre de contrôles à ancrer.|  
|[CFrameWnd::EndModalState](../Topic/CFrameWnd::EndModalState.md)|Termine l'état modal de la fenêtre frame.  Active toutes les fenêtres désactivées par `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)|Flotte une barre de contrôles.|  
|[CFrameWnd::GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md)|Retourne l'objet actif de **CDocument** .|  
|[CFrameWnd::GetActiveFrame](../Topic/CFrameWnd::GetActiveFrame.md)|Retourne l'objet actif d' `CFrameWnd` .|  
|[CFrameWnd::GetActiveView](../Topic/CFrameWnd::GetActiveView.md)|Retourne l'objet actif d' `CView` .|  
|[CFrameWnd::GetControlBar](../Topic/CFrameWnd::GetControlBar.md)|Extrait la barre de contrôles.|  
|[CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md)|Récupère l'état d'ancrage d'une fenêtre frame.|  
|[CFrameWnd::GetMenuBarState](../Topic/CFrameWnd::GetMenuBarState.md)|Récupère l'état d'affichage du menu de l'application actuelle MFC.|  
|[CFrameWnd::GetMenuBarVisibility](../Topic/CFrameWnd::GetMenuBarVisibility.md)|Indique si le comportement par défaut du menu de l'application actuelle MFC est masqué ou visible.|  
|[CFrameWnd::GetMessageBar](../Topic/CFrameWnd::GetMessageBar.md)|Retourne un pointeur vers la barre d'état appartenant à la fenêtre frame.|  
|[CFrameWnd::GetMessageString](../Topic/CFrameWnd::GetMessageString.md)|Récupère le message correspondant à un ID de commande|  
|[CFrameWnd::GetTitle](../Topic/CFrameWnd::GetTitle.md)|Récupère le titre de la barre de contrôles associée.|  
|[CFrameWnd::InitialUpdateFrame](../Topic/CFrameWnd::InitialUpdateFrame.md)|Provoque la fonction membre d' `OnInitialUpdate` appartenant à toutes les vues dans la fenêtre frame à appeler.|  
|[CFrameWnd::InModalState](../Topic/CFrameWnd::InModalState.md)|Retourne une valeur indiquant si une fenêtre frame est dans un état modal.|  
|[CFrameWnd::IsTracking](../Topic/CFrameWnd::IsTracking.md)|Détermine si la barre de fractionnement actuel est déplacée.|  
|[CFrameWnd::LoadAccelTable](../Topic/CFrameWnd::LoadAccelTable.md)|Appelez pour charger une table d'accélérateurs.|  
|[CFrameWnd::LoadBarState](../Topic/CFrameWnd::LoadBarState.md)|Appelez pour restaurer les paramètres de barres de contrôles.|  
|[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)|Appelez pour créer dynamiquement une fenêtre frame des informations sur les ressources.|  
|[CFrameWnd::NegotiateBorderSpace](../Topic/CFrameWnd::NegotiateBorderSpace.md)|Négocie l'espace de bordure de la fenêtre frame.|  
|[CFrameWnd::OnBarCheck](../Topic/CFrameWnd::OnBarCheck.md)|Appelé chaque fois qu'une action est exécutée sur la barre de contrôles spécifiée.|  
|[CFrameWnd::OnContextHelp](../Topic/CFrameWnd::OnContextHelp.md)|Utilisation de handles SHIFT\+F1 pour les éléments sur place.|  
|[CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)|Définit la fenêtre frame principale de l'application dans et hors de le mode aperçu avant impression.|  
|[CFrameWnd::OnUpdateControlBarMenu](../Topic/CFrameWnd::OnUpdateControlBarMenu.md)|Appelé par l'infrastructure lorsque le menu associé est mis à jour.|  
|[CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md)|Repositionne les barres de contrôles de l'objet d' `CFrameWnd` .|  
|[CFrameWnd::SaveBarState](../Topic/CFrameWnd::SaveBarState.md)|Appelez pour enregistrer les paramètres de barres de contrôles.|  
|[CFrameWnd::SetActivePreviewView](../Topic/CFrameWnd::SetActivePreviewView.md)|Indique la vue spécifiée comme étant la vue active pour l'aperçu riche.|  
|[CFrameWnd::SetActiveView](../Topic/CFrameWnd::SetActiveView.md)|Définit l'objet actif d' `CView` .|  
|[CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md)|Appelez pour ancrer la fenêtre frame dans la fenêtre principale.|  
|[CFrameWnd::SetMenuBarState](../Topic/CFrameWnd::SetMenuBarState.md)|Définit l'état d'affichage du menu de l'application actuelle MFC à masqué ou affiche.|  
|[CFrameWnd::SetMenuBarVisibility](../Topic/CFrameWnd::SetMenuBarVisibility.md)|Définit le comportement par défaut du menu de l'application actuelle MFC d'être masqué ou visible.|  
|[CFrameWnd::SetMessageText](../Topic/CFrameWnd::SetMessageText.md)|Définit le texte d'une barre d'état standard.|  
|[CFrameWnd::SetProgressBarPosition](../Topic/CFrameWnd::SetProgressBarPosition.md)|Définit la position actuelle pour la barre de progression Windows 7 affiche dans la barre des tâches.|  
|[CFrameWnd::SetProgressBarRange](../Topic/CFrameWnd::SetProgressBarRange.md)|Définit l'intervalle de la barre de progression Windows 7 affiche dans la barre des tâches.|  
|[CFrameWnd::SetProgressBarState](../Topic/CFrameWnd::SetProgressBarState.md)|Définit le type et l'état de l'indicateur de progression affiché sur un bouton de la barre des tâches.|  
|[CFrameWnd::SetTaskbarOverlayIcon](../Topic/CFrameWnd::SetTaskbarOverlayIcon.md)|Surchargé.  Applique une superposition à un bouton de la barre des tâches pour indiquer l'état de l'application ou une notification à l'utilisateur.|  
|[CFrameWnd::SetTitle](../Topic/CFrameWnd::SetTitle.md)|Définit le titre de la barre de contrôles associée.|  
|[CFrameWnd::ShowControlBar](../Topic/CFrameWnd::ShowControlBar.md)|Appelez pour afficher la barre de contrôles.|  
|[CFrameWnd::ShowOwnedWindows](../Topic/CFrameWnd::ShowOwnedWindows.md)|Affiche toutes les fenêtres qui sont des descendants de l'objet d' `CFrameWnd` .|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)|Crée une fenêtre cliente pour le frame.|  
|[CFrameWnd::OnHideMenuBar](../Topic/CFrameWnd::OnHideMenuBar.md)|Appelé avant le menu de l'application actuelle MFC est masqué.|  
|[CFrameWnd::OnShowMenuBar](../Topic/CFrameWnd::OnShowMenuBar.md)|Appelé avant le menu de l'application actuelle MFC s'affiche.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFrameWnd::m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md)|Les contrôles automatiques activent et désactivent la fonctionnalité des éléments de menu.|  
|[CFrameWnd::rectDefault](../Topic/CFrameWnd::rectDefault.md)|Passez cet `CRect` statique comme paramètre en créant un objet d' `CFrameWnd` pour permettre aux fenêtres pour choisir la taille et la position de la fenêtre.|  
  
## Notes  
 Pour créer une fenêtre frame utile pour votre application, dérivez une classe d' `CFrameWnd`.  Ajoutez des variables membres dans la classe dérivée au détail de données de mémoire à votre application.  Implémentez les fonctions membres gestionnaires de messages et une table des messages dans la classe dérivée pour spécifier ce qui se produit lorsque les messages sont dirigés vers la fenêtre.  
  
 Il existe trois façons de construire une fenêtre frame :  
  
-   Construisez\- directement à l'aide de la [Create](../Topic/CFrameWnd::Create.md).  
  
-   Construisez\- directement à l'aide de le [LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
-   Construisez\- indirectement l'utilisation d'un modèle de document.  
  
 Avant d'appeler **Créer** ou `LoadFrame`, vous devez construire l'objet de fenêtre frame sur le tas à l'aide de l'opérateur C\+\+ **nouveau** .  Avant d'appeler **Créer**, vous pouvez également enregistrer une classe de fenêtre avec la fonction globale d' [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) pour définir des styles d'icône et de classe pour le frame.  
  
 Utilisez la fonction membre de **Créer** pour passer des paramètres de la création du frame en tant qu'arguments immédiats.  
  
 `LoadFrame` requiert moins d'arguments que **Créer**, et extrait à la place la plupart de ses valeurs par défaut des ressources, y compris la légende du frame, l'icône, la table d'accélérateurs, et le menu.  Pour être accessibles par `LoadFrame`, toutes ces ressources doivent avoir le même ID de ressource \(par exemple, **IDR\_MAINFRAME**\).  
  
 Lorsqu'un objet d' `CFrameWnd` contient des vues et des documents, elles sont créées indirectement par l'infrastructure plutôt que directement par le programmeur.  l'objet d' `CDocTemplate` orchestre la création du frame, la création des vues contenantes, et la connexion des vues au document approprié.  Les paramètres du constructeur d' `CDocTemplate` spécifient `CRuntimeClass` les trois classes impliquées \(document, frame, et affichage\).  Un objet d' `CRuntimeClass` est utilisé par l'infrastructure pour créer dynamiquement de nouveaux frames une fois spécifié par l'utilisateur \(par exemple, en utilisant la nouvelle commande de fichier ou une commande de fenêtre d'interface multidocument \(MDI\) de la nouvelle\).  
  
 Une classe de fenêtre frame dérivée d' `CFrameWnd` doit être déclarée avec `DECLARE_DYNCREATE` pour que le mécanisme ci\-dessus d' `RUNTIME_CLASS` fonctionne correctement.  
  
 `CFrameWnd` contient des implémentations par défaut pour remplir les fonctions suivantes d'une fenêtre principale d'une application pour Windows classique :  
  
-   Une fenêtre frame d' `CFrameWnd` contient la vue active d'un actuel \(qui est indépendant de la fenêtre active windows ou du focus d'entrée actuel.  Lorsque le frame est réactivé, est averti la vue active en appelant `CView::OnActivateView`.  
  
-   Les messages de commande et de nombreux messages courants trames de notification, y compris ceux qui sont gérés par `OnSetFocus`, `OnHScroll`, et les fonctions d' `OnVScroll` d' `CWnd`, sont délégués par une fenêtre frame d' `CFrameWnd` actuel \- à la vue active.  
  
-   Actuel de la vue active \(ou actuel \- la fenêtre frame enfant MDI active dans le cas d'un frame MDI\) peut déterminer la légende de la fenêtre frame.  Cette fonctionnalité peut être désactivée en désactivant le bit de style de **FWS\_ADDTOTITLE** de la fenêtre frame.  
  
-   Une fenêtre frame d' `CFrameWnd` gère la position des barres de contrôles, des vues, et d'autres fenêtres enfants dans la zone cliente de la fenêtre frame.  Une fenêtre frame est également mettre à jour lorsque les temps d'inactivité de la barre d'outils et d'autres boutons de la barre de contrôle.  Une fenêtre frame d' `CFrameWnd` a également des implémentations par défaut des commandes pour basculer en activer et de désactiver la barre d'outils et la barre d'état.  
  
-   Une fenêtre frame d' `CFrameWnd` gère la barre de menu principal.  Lorsqu'un menu contextuel s'affiche, la fenêtre frame utilise le mécanisme d' **UPDATE\_COMMAND\_UI** pour déterminer les éléments de menu doivent être activés, désactivés, ou activées.  Lorsque l'utilisateur sélectionne un élément de menu, la fenêtre frame met à jour la barre d'état et la chaîne de message pour cette commande.  
  
-   Une fenêtre frame d' `CFrameWnd` a une table d'accélérateurs facultative qui convertit automatiquement les accélérateurs de clavier.  
  
-   Une fenêtre frame d' `CFrameWnd` a un ID d'aide facultatif défini avec `LoadFrame` utilisé pour obtenir de l'aide contextuelle.  Une fenêtre frame est l'orchestrateur principal des rapports semimodal tels que les modes de l'aide contextuelle \(SHIFT\+F1\) et de l'aperçu avant impression.  
  
-   Une fenêtre frame d' `CFrameWnd` ouvre un fichier déplacée du gestionnaire de fichiers et supprimé de la fenêtre frame.  Si une extension de fichier est stockée et associée à l'application, la fenêtre frame répond à la requête ouverte de \(DDE\) échange dynamique de données qui se produit lorsque l'utilisateur ouvre un fichier de données dans le gestionnaire de fichiers ou lorsque la fonction Windows de **ShellExecute** est appelée.  
  
-   Si la fenêtre frame est la fenêtre d'application principale \(autrement dit, `CWinThread::m_pMainWnd`\), lorsque l'utilisateur ferme l'application, la fenêtre frame invite l'utilisateur à enregistrer tous les documents modifiés \(pour `OnClose` et `OnQueryEndSession`\).  
  
-   Si la fenêtre frame est la fenêtre d'application principale, la fenêtre frame est le contexte d'exécution WinHelp.  La fermeture de la fenêtre frame arrête WINHELP.EXE s'il a été activé pour une assistance pour cette application.  
  
 N'utilisez pas l'opérateur C\+\+ **supprimer** pour détruire une fenêtre frame.  Utilisez plutôt `CWnd::DestroyWindow`.  L'implémentation d' `CFrameWnd` d' `PostNcDestroy` supprimera l'objet C\+\+ lorsque la fenêtre est détruite.  Lorsque l'utilisateur ferme la fenêtre frame, le gestionnaire par défaut d' `OnClose` appelle `DestroyWindow`.  
  
 Pour plus d'informations sur `CFrameWnd`, consultez [fenêtres frames](../../mfc/frame-windows.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md)