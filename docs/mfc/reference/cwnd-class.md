---
title: "CWnd, classe | Microsoft Docs"
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
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd (classe)"
  - "window objects [C++]"
  - "windows [C++]"
ms.assetid: 49a832ee-bc34-4126-88b3-bc1d9974f6c4
caps.latest.revision: 27
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWnd, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de base de toutes les classes de fenêtres de la bibliothèque MFC \(Microsoft Foundation Class\).  
  
## Syntaxe  
  
```  
class CWnd : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWnd::CWnd](../Topic/CWnd::CWnd.md)|Construit un objet `CWnd`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWnd::accDoDefaultAction](../Topic/CWnd::accDoDefaultAction.md)|Appelé par l'infrastructure pour effectuer l'action par défaut de l'objet.|  
|[CWnd::accHitTest](../Topic/CWnd::accHitTest.md)|Appelé par l'infrastructure pour récupérer l'élément enfant ou l'objet enfant à un point déterminé de l'écran.|  
|[CWnd::accLocation](../Topic/CWnd::accLocation.md)|Appelé par l'infrastructure pour récupérer l'emplacement d'affichage actuel de l'objet spécifié.|  
|[CWnd::accNavigate](../Topic/CWnd::accNavigate.md)|Appelé par l'infrastructure pour accéder à un autre élément d'interface utilisateur au sein d'un conteneur et, dans la mesure du possible, récupérer l'objet.|  
|[CWnd::accSelect](../Topic/CWnd::accSelect.md)|Appelé par l'infrastructure pour modifier la sélection ou déplacer le focus clavier de l'objet spécifié.|  
|[CWnd::AnimateWindow](../Topic/CWnd::AnimateWindow.md)|Anime l'objet fenêtre associé.|  
|[CWnd::ArrangeIconicWindows](../Topic/CWnd::ArrangeIconicWindows.md)|Réorganise toutes les fenêtres enfants réduites \(sous forme d'icônes\).|  
|[CWnd::Attach](../Topic/CWnd::Attach.md)|Attache un handle Windows à un objet `CWnd`.|  
|[CWnd::BeginModalState](../Topic/CWnd::BeginModalState.md)|Appelez cette fonction membre pour rendre modale une fenêtre frame.|  
|[CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md)|Prépare `CWnd` pour la peinture.|  
|[CWnd::BindDefaultProperty](../Topic/CWnd::BindDefaultProperty.md)|Lie la propriété liée simple par défaut de l'objet appelant, comme indiqué dans la bibliothèque de types, à un curseur associé à un contrôle de source de données.|  
|[CWnd::BindProperty](../Topic/CWnd::BindProperty.md)|Lie une propriété liée au curseur d'un contrôle lié aux données à un contrôle de source de données et inscrit cette relation auprès du gestionnaire de liaisons MFC.|  
|[CWnd::BringWindowToTop](../Topic/CWnd::BringWindowToTop.md)|Place `CWnd` en haut d'une pile de fenêtres superposées.|  
|[CWnd::CalcWindowRect](../Topic/CWnd::CalcWindowRect.md)|Appelé pour calculer le rectangle de la fenêtre à partir du rectangle client.|  
|[CWnd::CancelToolTips](../Topic/CWnd::CancelToolTips.md)|Désactive le contrôle d'info\-bulle.|  
|[CWnd::CenterWindow](../Topic/CWnd::CenterWindow.md)|Centre une fenêtre par rapport à son parent.|  
|[CWnd::ChangeClipboardChain](../Topic/CWnd::ChangeClipboardChain.md)|Supprime `CWnd` de la chaîne de visionneuses de Presse\-papiers.|  
|[CWnd::CheckDlgButton](../Topic/CWnd::CheckDlgButton.md)|Place une coche à côté d'un contrôle bouton ou la supprime.|  
|[CWnd::CheckRadioButton](../Topic/CWnd::CheckRadioButton.md)|Vérifie la case d'option spécifiée et supprime la coche de toutes les autres cases d'option contenues dans le groupe de boutons spécifié.|  
|[CWnd::ChildWindowFromPoint](../Topic/CWnd::ChildWindowFromPoint.md)|Parmi les fenêtres enfants existantes, détermine celles qui contiennent le point spécifié, le cas échéant.|  
|[CWnd::ClientToScreen](../Topic/CWnd::ClientToScreen.md)|Convertit les coordonnées clientes d'un point ou rectangle donné affiché en coordonnées d'écran.|  
|[CWnd::CloseWindow](../Topic/CWnd::CloseWindow.md)|Réduit la fenêtre.|  
|[CWnd::ContinueModal](../Topic/CWnd::ContinueModal.md)|Conserve l'état modal d'une fenêtre.|  
|[CWnd::Create](../Topic/CWnd::Create.md)|Crée et initialise la fenêtre enfant associée à l'objet `CWnd`.|  
|[CWnd::CreateAccessibleProxy](../Topic/CWnd::CreateAccessibleProxy.md)|Crée un proxy Active Accessibility pour l'objet spécifié.|  
|[CWnd::CreateCaret](../Topic/CWnd::CreateCaret.md)|Crée une forme pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::CreateControl](../Topic/CWnd::CreateControl.md)|Crée un contrôle ActiveX qui sera représenté dans un programme MFC par un objet `CWnd`.|  
|[CWnd::CreateEx](../Topic/CWnd::CreateEx.md)|Crée une fenêtre Windows superposée, indépendante ou enfant et l'attache à un objet `CWnd`.|  
|[CWnd::CreateGrayCaret](../Topic/CWnd::CreateGrayCaret.md)|Crée un bloc gris pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::CreateSolidCaret](../Topic/CWnd::CreateSolidCaret.md)|Crée un bloc uni pour le signe insertion et obtient la propriété du caret.|  
|[CWnd::DeleteTempMap](../Topic/CWnd::DeleteTempMap.md)|Appelé automatiquement par le gestionnaire de durée d'inactivité `CWinApp` et supprime les objets `CWnd` temporaires créés par `FromHandle`.|  
|[CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md)|Détruit la fenêtre Windows attachée.|  
|[CWnd::Detach](../Topic/CWnd::Detach.md)|Détache un handle Windows d'un objet `CWnd` et retourne le handle.|  
|[CWnd::DlgDirList](../Topic/CWnd::DlgDirList.md)|Remplit une zone de liste avec une liste de fichiers ou de répertoires.|  
|[CWnd::DlgDirListComboBox](../Topic/CWnd::DlgDirListComboBox.md)|Remplit la zone de liste d'une zone de liste modifiable avec une liste de fichiers ou de répertoires.|  
|[CWnd::DlgDirSelect](../Topic/CWnd::DlgDirSelect.md)|Récupère la sélection actuelle d'une zone de liste.|  
|[CWnd::DlgDirSelectComboBox](../Topic/CWnd::DlgDirSelectComboBox.md)|Récupère la sélection actuelle de la zone de liste d'une zone de liste modifiable.|  
|[CWnd::DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md)|Indique que la fenêtre acceptera les fichiers déplacés.|  
|[CWnd::DragDetect](../Topic/CWnd::DragDetect.md)|Capture la souris et suit ses déplacements jusqu'à ce que l'utilisateur relâche le bouton gauche, appuie sur la touche Échap ou déplace la souris en dehors du rectangle de glissement entourant le point spécifié.|  
|[CWnd::DrawAnimatedRects](../Topic/CWnd::DrawAnimatedRects.md)|Dessine un rectangle en mode filaire et l'anime pour indiquer l'ouverture d'une icône ou la réduction ou agrandissement d'une fenêtre.|  
|[CWnd::DrawCaption](../Topic/CWnd::DrawCaption.md)|Dessine une légende.|  
|[CWnd::DrawMenuBar](../Topic/CWnd::DrawMenuBar.md)|Redessine la barre de menus.|  
|[CWnd::EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md)|Active les fonctions `Active Accessibility` définies par l'utilisateur.|  
|[CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md)|Active la position et la taille des fenêtres enfants pour qu'elles s'ajustent dynamiquement quand l'utilisateur redimensionne la fenêtre.|  
|[CWnd::EnableD2DSupport](../Topic/CWnd::EnableD2DSupport.md)|Active ou désactive la prise en charge `D2D` de la fenêtre.  Appelez cette méthode avant que la fenêtre principale soit initialisée.|  
|[CWnd::EnableScrollBar](../Topic/CWnd::EnableScrollBar.md)|Active ou désactive une flèche \(ou les deux\) d'une barre de défilement.|  
|[CWnd::EnableScrollBarCtrl](../Topic/CWnd::EnableScrollBarCtrl.md)|Active ou désactive un contrôle de barre de défilement frère.|  
|[CWnd::EnableToolTips](../Topic/CWnd::EnableToolTips.md)|Active le contrôle d'info\-bulle.|  
|[CWnd::EnableTrackingToolTips](../Topic/CWnd::EnableTrackingToolTips.md)|Active le contrôle d'info\-bulle en mode de suivi.|  
|[CWnd::EnableWindow](../Topic/CWnd::EnableWindow.md)|Active ou désactive les entrées de souris et de clavier.|  
|[CWnd::EndModalLoop](../Topic/CWnd::EndModalLoop.md)|Met fin à l'état modal d'une fenêtre.|  
|[CWnd::EndModalState](../Topic/CWnd::EndModalState.md)|Appelez cette fonction membre pour changer une fenêtre frame modale en fenêtre frame non modale.|  
|[CWnd::EndPaint](../Topic/CWnd::EndPaint.md)|Marque la fin de la peinture.|  
|[CWnd::ExecuteDlgInit](../Topic/CWnd::ExecuteDlgInit.md)|Initie une ressource de boîte de dialogue|  
|[CWnd::FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md)|Récupère le titre ou le texte associé à un contrôle de boîte de dialogue.|  
|[CWnd::FindWindow](../Topic/CWnd::FindWindow.md)|Retourne le handle de la fenêtre, qui est identifiée par ses nom et classe de fenêtre.|  
|[CWnd::FindWindowEx](../Topic/CWnd::FindWindowEx.md)|Retourne le handle de la fenêtre, qui est identifiée par ses nom et classe de fenêtre.|  
|[CWnd::FlashWindow](../Topic/CWnd::FlashWindow.md)|Fait clignoter la fenêtre une fois.|  
|[CWnd::FlashWindowEx](../Topic/CWnd::FlashWindowEx.md)|Fait clignoter la fenêtre avec des fonctionnalités supplémentaires.|  
|[CWnd::FromHandle](../Topic/CWnd::FromHandle.md)|Retourne un pointeur vers un objet `CWnd` quand un handle de fenêtre lui est fourni.  Si aucun objet `CWnd` n'est attaché au handle, un objet `CWnd` temporaire est créé et attaché.|  
|[CWnd::FromHandlePermanent](../Topic/CWnd::FromHandlePermanent.md)|Retourne un pointeur vers un objet `CWnd` quand un handle de fenêtre lui est fourni.  Si aucun objet `CWnd` n'est attaché au handle, un objet `CWnd` temporaire est créé et attaché.|  
|[CWnd::get\_accChild](../Topic/CWnd::get_accChild.md)|Appelé par l'infrastructure pour récupérer l'adresse d'une interface `IDispatch` pour l'enfant spécifié.|  
|[CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md)|Appelé par l'infrastructure pour récupérer le nombre d'enfants appartenant à cet objet.|  
|[CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md)|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'action par défaut de l'objet.|  
|[CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md)|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'aspect visuel de l'objet spécifié.|  
|[CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md)|Appelé par l'infrastructure pour récupérer l'objet qui a le focus clavier.|  
|[CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md)|Appelé par l'infrastructure pour récupérer la chaîne de propriété **Help** d'un objet.|  
|[CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md)|Appelé par l'infrastructure pour récupérer le chemin d'accès complet du fichier `WinHelp` associé à l'objet spécifié, ainsi que l'identificateur de la rubrique appropriée au sein de ce fichier.|  
|[CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md)|Appelé par l'infrastructure pour récupérer la touche de raccourci ou la touche d'accès rapide de l'objet spécifié.|  
|[CWnd::get\_accName](../Topic/CWnd::get_accName.md)|Appelé par l'infrastructure pour récupérer le nom de l'objet spécifié.|  
|[CWnd::get\_accParent](../Topic/CWnd::get_accParent.md)|Appelé par l'infrastructure pour récupérer l'interface `IDispatch` du parent de l'objet.|  
|[CWnd::get\_accRole](../Topic/CWnd::get_accRole.md)|Appelé par l'infrastructure pour récupérer les informations qui décrivent le rôle de l'objet spécifié.|  
|[CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md)|Appelé par l'infrastructure pour récupérer les enfants sélectionnés de cet objet.|  
|[CWnd::get\_accState](../Topic/CWnd::get_accState.md)|Appelé par l'infrastructure pour récupérer l'état actuel de l'objet spécifié.|  
|[CWnd::get\_accValue](../Topic/CWnd::get_accValue.md)|Appelé par l'infrastructure pour récupérer la valeur de l'objet spécifié.|  
|[CWnd::GetActiveWindow](../Topic/CWnd::GetActiveWindow.md)|Récupère la fenêtre active.|  
|[CWnd::GetAncestor](../Topic/CWnd::GetAncestor.md)|Récupère l'objet fenêtre ancêtre de la fenêtre spécifiée.|  
|[CWnd::GetCapture](../Topic/CWnd::GetCapture.md)|Récupère le `CWnd` qui détient la capture de souris.|  
|[CWnd::GetCaretPos](../Topic/CWnd::GetCaretPos.md)|Récupère les coordonnées clientes de la position actuelle du caret.|  
|[CWnd::GetCheckedRadioButton](../Topic/CWnd::GetCheckedRadioButton.md)|Retourne l'ID de la case d'option actuellement activée dans un groupe de boutons.|  
|[CWnd::GetClientRect](../Topic/CWnd::GetClientRect.md)|Obtient les dimensions de la zone cliente `CWnd`.|  
|[CWnd::GetClipboardOwner](../Topic/CWnd::GetClipboardOwner.md)|Récupère un pointeur désignant le propriétaire actuel du Presse\-papiers.|  
|[CWnd::GetClipboardViewer](../Topic/CWnd::GetClipboardViewer.md)|Récupère un pointeur désignant la première fenêtre de la chaîne de visionneuses de Presse\-papiers.|  
|[CWnd::GetControlUnknown](../Topic/CWnd::GetControlUnknown.md)|Récupère un pointeur vers un contrôle ActiveX inconnu.|  
|[CWnd::GetDC](../Topic/CWnd::GetDC.md)|Récupère un contexte d'affichage pour la zone cliente.|  
|[CWnd::GetDCEx](../Topic/CWnd::GetDCEx.md)|Récupère un contexte d'affichage pour la zone cliente et active le détourage pendant le traçage du dessin.|  
|[CWnd::GetDCRenderTarget](../Topic/CWnd::GetDCRenderTarget.md)|Récupère la cible de rendu du contexte de périphérique pour la fenêtre `CWnd`.|  
|[CWnd::GetDescendantWindow](../Topic/CWnd::GetDescendantWindow.md)|Recherche dans toutes les fenêtres descendantes et retourne la fenêtre ayant l'ID spécifié.|  
|[CWnd::GetDesktopWindow](../Topic/CWnd::GetDesktopWindow.md)|Récupère la fenêtre du bureau Windows.|  
|[CWnd::GetDlgCtrlID](../Topic/CWnd::GetDlgCtrlID.md)|Si `CWnd` est une fenêtre enfant, l'appel de cette fonction retourne sa valeur d'ID.|  
|[CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md)|Récupère le contrôle ayant l'ID spécifié dans la boîte de dialogue spécifiée.|  
|[CWnd::GetDlgItemInt](../Topic/CWnd::GetDlgItemInt.md)|Traduit le texte d'un contrôle de la boîte de dialogue spécifiée en valeur entière.|  
|[CWnd::GetDlgItemText](../Topic/CWnd::GetDlgItemText.md)|Récupère la légende ou le texte associé à un contrôle.|  
|[CWnd::GetDSCCursor](../Topic/CWnd::GetDSCCursor.md)|Récupère un pointeur désignant le curseur sous\-jacent défini par les propriétés DataSource, UserName, Password et SQL d'un contrôle de source de données.|  
|[CWnd::GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md)|Récupère un pointeur désignant l'objet gestionnaire de disposition dynamique.|  
|[CWnd::GetExStyle](../Topic/CWnd::GetExStyle.md)|Retourne le style étendu de la fenêtre.|  
|[CWnd::GetFocus](../Topic/CWnd::GetFocus.md)|Récupère le `CWnd` qui a actuellement le focus d'entrée.|  
|[CWnd::GetFont](../Topic/CWnd::GetFont.md)|Récupère la police actuelle.|  
|[CWnd::GetForegroundWindow](../Topic/CWnd::GetForegroundWindow.md)|Retourne un pointeur désignant la fenêtre de premier plan \(fenêtre de niveau supérieur dans laquelle l'utilisateur travaille actuellement\).|  
|[CWnd::GetIcon](../Topic/CWnd::GetIcon.md)|Récupère le handle d'une icône.|  
|[CWnd::GetLastActivePopup](../Topic/CWnd::GetLastActivePopup.md)|Identifie la dernière fenêtre contextuelle détenue par `CWnd` à avoir été active.|  
|[CWnd::GetLayeredWindowAttributes](../Topic/CWnd::GetLayeredWindowAttributes.md)|Récupère la clé de couleur d'opacité et de transparence d'une fenêtre superposée.|  
|[CWnd::GetMenu](../Topic/CWnd::GetMenu.md)|Récupère un pointeur vers le menu spécifié.|  
|[CWnd::GetNextDlgGroupItem](../Topic/CWnd::GetNextDlgGroupItem.md)|Recherche le contrôle suivant \(ou précédent\) au sein d'un groupe de contrôles.|  
|[CWnd::GetNextDlgTabItem](../Topic/CWnd::GetNextDlgTabItem.md)|Récupère le premier contrôle ayant le style [WS\_TABSTOP](../../mfc/reference/window-styles.md) suivant \(ou précédant\) le contrôle spécifié.|  
|[CWnd::GetNextWindow](../Topic/CWnd::GetNextWindow.md)|Retourne la fenêtre suivante \(ou précédente\) dans la liste du gestionnaire de fenêtrage.|  
|[CWnd::GetOleControlSite](../Topic/CWnd::GetOleControlSite.md)|Récupère le site personnalisé pour le contrôle ActiveX spécifié.|  
|[CWnd::GetOpenClipboardWindow](../Topic/CWnd::GetOpenClipboardWindow.md)|Récupère un pointeur vers la fenêtre pour laquelle le Presse\-papiers est actuellement ouvert.|  
|[CWnd::GetOwner](../Topic/CWnd::GetOwner.md)|Récupère un pointeur vers le propriétaire d'un `CWnd`.|  
|[CWnd::GetParent](../Topic/CWnd::GetParent.md)|Récupère la fenêtre parente de `CWnd` \(le cas échéant\).|  
|[CWnd::GetParentFrame](../Topic/CWnd::GetParentFrame.md)|Récupère la fenêtre frame parente de l'objet `CWnd`.|  
|[CWnd::GetParentOwner](../Topic/CWnd::GetParentOwner.md)|Retourne un pointeur vers la fenêtre parente d'une fenêtre enfant.|  
|[CWnd::GetProperty](../Topic/CWnd::GetProperty.md)|Récupère une propriété de contrôle ActiveX.|  
|[CWnd::GetRenderTarget](../Topic/CWnd::GetRenderTarget.md)|Obtient une cible de rendu associée à cette fenêtre.|  
|[CWnd::GetSafeHwnd](../Topic/CWnd::GetSafeHwnd.md)|Retourne `m_hWnd` ou `NULL` si le pointeur `this` a la valeur `NULL`.|  
|[CWnd::GetSafeOwner](../Topic/CWnd::GetSafeOwner.md)|Récupère le propriétaire sécurisé pour la fenêtre spécifiée.|  
|[CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md)|Retourne un contrôle de barre de défilement frère.|  
|[CWnd::GetScrollBarInfo](../Topic/CWnd::GetScrollBarInfo.md)|Récupère les informations sur la barre de défilement spécifiée.|  
|[CWnd::GetScrollInfo](../Topic/CWnd::GetScrollInfo.md)|Récupère les informations que la structure `SCROLLINFO` conserve à propos d'une barre de défilement.|  
|[CWnd::GetScrollLimit](../Topic/CWnd::GetScrollLimit.md)|Récupère la limite de la barre de défilement.|  
|[CWnd::GetScrollPos](../Topic/CWnd::GetScrollPos.md)|Récupère la position actuelle d'une case de défilement.|  
|[CWnd::GetScrollRange](../Topic/CWnd::GetScrollRange.md)|Copie les positions minimale et maximale actuelles de la barre de défilement spécifiée.|  
|[CWnd::GetStyle](../Topic/CWnd::GetStyle.md)|Retourne le style de fenêtre actif.|  
|[CWnd::GetSystemMenu](../Topic/CWnd::GetSystemMenu.md)|Permet à l'application d'accéder au menu Système pour copie et modification.|  
|[CWnd::GetTitleBarInfo](../Topic/CWnd::GetTitleBarInfo.md)|Récupère les informations sur la barre de titre spécifiée.|  
|[CWnd::GetTopLevelFrame](../Topic/CWnd::GetTopLevelFrame.md)|Récupère la fenêtre frame de niveau supérieur de la fenêtre.|  
|[CWnd::GetTopLevelOwner](../Topic/CWnd::GetTopLevelOwner.md)|Récupère la fenêtre de niveau supérieur.|  
|[CWnd::GetTopLevelParent](../Topic/CWnd::GetTopLevelParent.md)|Récupère le parent de niveau supérieur de la fenêtre.|  
|[CWnd::GetTopWindow](../Topic/CWnd::GetTopWindow.md)|Retourne la première fenêtre enfant qui appartient à `CWnd`.|  
|[CWnd::GetUpdateRect](../Topic/CWnd::GetUpdateRect.md)|Récupère les coordonnées du plus petit rectangle qui englobe entièrement la région de mise à jour `CWnd`.|  
|[CWnd::GetUpdateRgn](../Topic/CWnd::GetUpdateRgn.md)|Récupère la région de mise à jour `CWnd`.|  
|[CWnd::GetWindow](../Topic/CWnd::GetWindow.md)|Retourne la fenêtre avec la relation spécifiée de cette fenêtre.|  
|[CWnd::GetWindowContextHelpId](../Topic/CWnd::GetWindowContextHelpId.md)|Récupère l'identificateur de contexte d'aide.|  
|[CWnd::GetWindowDC](../Topic/CWnd::GetWindowDC.md)|Récupère le contexte d'affichage de la fenêtre entière, y compris la barre de légende, les menus et les barres de défilement.|  
|[CWnd::GetWindowedChildCount](../Topic/CWnd::GetWindowedChildCount.md)|Retourne le nombre de fenêtres enfants associées.|  
|[CWnd::GetWindowInfo](../Topic/CWnd::GetWindowInfo.md)|Retourne les informations sur la fenêtre.|  
|[CWnd::GetWindowlessChildCount](../Topic/CWnd::GetWindowlessChildCount.md)|Retourne le nombre de fenêtres enfants sans fenêtre associées.|  
|[CWnd::GetWindowPlacement](../Topic/CWnd::GetWindowPlacement.md)|Récupère l'état d'affichage et les positions normale \(restaurée\), réduite et agrandie d'une fenêtre.|  
|[CWnd::GetWindowRect](../Topic/CWnd::GetWindowRect.md)|Obtient les coordonnées d'écran de `CWnd`.|  
|[CWnd::GetWindowRgn](../Topic/CWnd::GetWindowRgn.md)|Récupère une copie de la région de fenêtre d'une fenêtre.|  
|[CWnd::GetWindowText](../Topic/CWnd::GetWindowText.md)|Retourne le texte de la fenêtre ou le titre de la légende \(le cas échéant\).|  
|[CWnd::GetWindowTextLength](../Topic/CWnd::GetWindowTextLength.md)|Retourne la longueur du texte de la fenêtre ou du titre de légende.|  
|[CWnd::HideCaret](../Topic/CWnd::HideCaret.md)|Masque le caret en le supprimant de l'écran.|  
|[CWnd::HiliteMenuItem](../Topic/CWnd::HiliteMenuItem.md)|Met en surbrillance ou supprime la mise en surbrillance d'un élément de menu \(barre de menus\) de niveau supérieur.|  
|[CWnd::HtmlHelp](../Topic/CWnd::HtmlHelp.md)|Appelé pour lancer l'application HTMLHelp.|  
|[CWnd::Invalidate](../Topic/CWnd::Invalidate.md)|Invalide la zone cliente dans son intégralité.|  
|[CWnd::InvalidateRect](../Topic/CWnd::InvalidateRect.md)|Invalide la zone cliente dans le rectangle donné en ajoutant ce rectangle à la région de mise à jour actuelle.|  
|[CWnd::InvalidateRgn](../Topic/CWnd::InvalidateRgn.md)|Invalide la zone cliente dans la région en question donnée en ajoutant cette région à la région de mise à jour actuelle.|  
|[CWnd::InvokeHelper](../Topic/CWnd::InvokeHelper.md)|Appelle une méthode ou une propriété de contrôle ActiveX.|  
|[CWnd::IsChild](../Topic/CWnd::IsChild.md)|Indique si `CWnd` est une fenêtre enfant ou un autre descendant direct de la fenêtre spécifiée.|  
|[CWnd::IsD2DSupportEnabled](../Topic/CWnd::IsD2DSupportEnabled.md)|Détermine si la prise en charge `D2D` est activée.|  
|[CWnd::IsDialogMessage](../Topic/CWnd::IsDialogMessage.md)|Détermine si le message donné est destiné à la boîte de dialogue non modale et, si tel est le cas, le traite.|  
|[CWnd::IsDlgButtonChecked](../Topic/CWnd::IsDlgButtonChecked.md)|Détermine si un contrôle bouton est activé.|  
|[CWnd::IsDynamicLayoutEnabled](../Topic/CWnd::IsDynamicLayoutEnabled.md)|Détermine si la disposition dynamique est activée dans cette fenêtre.  Si la disposition dynamique est activée, la position et la taille des fenêtres enfants peuvent changer quand l'utilisateur redimensionne la fenêtre parente.|  
|[CWnd::IsIconic](../Topic/CWnd::IsIconic.md)|Détermine si `CWnd` est réduit \(sous forme d'icône\).|  
|[CWnd::IsTouchWindow](../Topic/CWnd::IsTouchWindow.md)|Spécifie si `CWnd` intègre une prise en charge de l'interface tactile.|  
|[CWnd::IsWindowEnabled](../Topic/CWnd::IsWindowEnabled.md)|Détermine si la fenêtre est activée pour les entrées de souris et de clavier.|  
|[CWnd::IsWindowVisible](../Topic/CWnd::IsWindowVisible.md)|Détermine si la fenêtre est visible.|  
|[CWnd::IsZoomed](../Topic/CWnd::IsZoomed.md)|Détermine si `CWnd` est agrandi.|  
|[CWnd::KillTimer](../Topic/CWnd::KillTimer.md)|Arrête une horloge système.|  
|[CWnd::LockWindowUpdate](../Topic/CWnd::LockWindowUpdate.md)|Désactive ou réactive un dessin dans la fenêtre donnée.|  
|[CWnd::MapWindowPoints](../Topic/CWnd::MapWindowPoints.md)|Convertit \(mappe\) un ensemble de points de l'espace de coordonnées de `CWnd` dans celui d'une autre fenêtre.|  
|[CWnd::MessageBox](../Topic/CWnd::MessageBox.md)|Crée et affiche une fenêtre qui contient un message et une légende fournis par l'application.|  
|[CWnd::ModifyStyle](../Topic/CWnd::ModifyStyle.md)|Modifie le style de fenêtre actif.|  
|[CWnd::ModifyStyleEx](../Topic/CWnd::ModifyStyleEx.md)|Modifie le style étendu de la fenêtre.|  
|[CWnd::MoveWindow](../Topic/CWnd::MoveWindow.md)|Modifie la position et les dimensions de `CWnd`.|  
|[CWnd::NotifyWinEvent](../Topic/CWnd::NotifyWinEvent.md)|Signale au système qu'un événement prédéfini s'est produit.|  
|[CWnd::OnAmbientProperty](../Topic/CWnd::OnAmbientProperty.md)|Implémente les valeurs de propriété ambiante.|  
|[CWnd::OnDrawIconicThumbnailOrLivePreview](../Topic/CWnd::OnDrawIconicThumbnailOrLivePreview.md)|Appelé par l'infrastructure quand elle a besoin d'obtenir une image bitmap à afficher sur une miniature d'onglet Windows 7 ou sur le client pour l'aperçu de l'application.|  
|[CWnd::OnHelp](../Topic/CWnd::OnHelp.md)|Gère l'aide F1 dans l'application \(en utilisant le contexte actuel\).|  
|[CWnd::OnHelpFinder](../Topic/CWnd::OnHelpFinder.md)|Gère les commandes `ID_HELP_FINDER` et `ID_DEFAULT_HELP`.|  
|[CWnd::OnHelpIndex](../Topic/CWnd::OnHelpIndex.md)|Gère la commande `ID_HELP_INDEX` et fournit une rubrique d'aide par défaut.|  
|[CWnd::OnHelpUsing](../Topic/CWnd::OnHelpUsing.md)|Gère la commande `ID_HELP_USING`.|  
|[CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md)|Détermine si un point se trouve dans le rectangle englobant de l'outil spécifié et récupère les informations sur l'outil.|  
|[CWnd::OpenClipboard](../Topic/CWnd::OpenClipboard.md)|Ouvre le Presse\-papiers.  Les autres applications ne pourront pas modifier le Presse\-papiers tant que la fonction [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) de Windows n'aura pas été appelée.|  
|[CWnd::PaintWindowlessControls](../Topic/CWnd::PaintWindowlessControls.md)|Dessine des contrôles sans fenêtre sur le conteneur de contrôle.|  
|[CWnd::PostMessage](../Topic/CWnd::PostMessage.md)|Place un message dans la file d'attente d'application, puis retourne une valeur sans attendre que la fenêtre ait traité le message.|  
|[CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)|Appelé avant la création de la fenêtre Windows attachée à cet objet `CWnd`.|  
|[CWnd::PreSubclassWindow](../Topic/CWnd::PreSubclassWindow.md)|Autorise un autre sous\-classement nécessaire avant l'appel de [SubclassWindow](../Topic/CWnd::SubclassWindow.md).|  
|[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)|Utilisé par `CWinApp` pour filtrer les messages de fenêtre avant d'être distribués aux fonctions Windows `TranslateMessage` et `DispatchMessage`.|  
|[CWnd::Print](../Topic/CWnd::Print.md)|Dessine la fenêtre active dans le contexte de périphérique spécifié.|  
|[CWnd::PrintClient](../Topic/CWnd::PrintClient.md)|Dessine une fenêtre dans le contexte de périphérique spécifié \(généralement un contexte de périphérique d'impression\).|  
|[CWnd::PrintWindow](../Topic/CWnd::PrintWindow.md)|Copie une fenêtre visuelle dans le contexte de périphérique spécifié, en général un contexte de périphérique d'impression.|  
|[CWnd::RedrawWindow](../Topic/CWnd::RedrawWindow.md)|Met à jour la région ou le rectangle spécifié dans la zone cliente.|  
|[CWnd::RegisterTouchWindow](../Topic/CWnd::RegisterTouchWindow.md)|Inscrit\/annule l'inscription de la prise en charge de l'interface tactile Windows de fenêtre.|  
|[CWnd::ReleaseDC](../Topic/CWnd::ReleaseDC.md)|Libère les contextes de périphérique client et fenêtre, ce qui les libère en vue d'une utilisation par d'autres applications.|  
|[CWnd::RepositionBars](../Topic/CWnd::RepositionBars.md)|Repositionne les barres de contrôle dans la zone cliente.|  
|[CWnd::RunModalLoop](../Topic/CWnd::RunModalLoop.md)|Récupère, traduit ou distribue les messages pour une fenêtre qui est à l'état modal.|  
|[CWnd::ScreenToClient](../Topic/CWnd::ScreenToClient.md)|Convertit les coordonnées d'écran d'un point ou rectangle donné sur l'affichage en coordonnées clientes.|  
|[CWnd::ScrollWindow](../Topic/CWnd::ScrollWindow.md)|Fait défiler le contenu de la zone cliente.|  
|[CWnd::ScrollWindowEx](../Topic/CWnd::ScrollWindowEx.md)|Fait défiler le contenu de la zone cliente.  Semblable à `ScrollWindow` avec des fonctionnalités supplémentaires.|  
|[CWnd::SendChildNotifyLastMsg](../Topic/CWnd::SendChildNotifyLastMsg.md)|Fournit un message de notification à une fenêtre enfant, à partir de la fenêtre parente, pour que la fenêtre enfant puisse gérer une tâche.|  
|[CWnd::SendDlgItemMessage](../Topic/CWnd::SendDlgItemMessage.md)|Envoie un message au contrôle spécifié.|  
|[CWnd::SendMessage](../Topic/CWnd::SendMessage.md)|Envoie un message à l'objet `CWnd` et ne retourne pas de valeur tant qu'il n'a pas traité le message.|  
|[CWnd::SendMessageToDescendants](../Topic/CWnd::SendMessageToDescendants.md)|Envoie un message à toutes les fenêtres descendantes de la fenêtre.|  
|[CWnd::SendNotifyMessage](../Topic/CWnd::SendNotifyMessage.md)|Envoie le message spécifié à la fenêtre et retourne une valeur dès que possible, selon que le thread appelant a créé ou non la fenêtre.|  
|[CWnd::SetActiveWindow](../Topic/CWnd::SetActiveWindow.md)|Active la fenêtre.|  
|[CWnd::SetCapture](../Topic/CWnd::SetCapture.md)|Provoque l'envoi de toutes les entrées de souris ultérieures à `CWnd`.|  
|[CWnd::SetCaretPos](../Topic/CWnd::SetCaretPos.md)|Déplace le caret vers une position spécifiée.|  
|[CWnd::SetClipboardViewer](../Topic/CWnd::SetClipboardViewer.md)|Ajoute `CWnd` à la chaîne de fenêtres qui sont notifiées chaque fois que le contenu du Presse\-papiers est modifié.|  
|[CWnd::SetDlgCtrlID](../Topic/CWnd::SetDlgCtrlID.md)|Définit l'ID de fenêtre ou l'ID de contrôle de la fenêtre \(qui peut être une fenêtre enfant, et pas seulement un contrôle de boîte de dialogue\).|  
|[CWnd::SetDlgItemInt](../Topic/CWnd::SetDlgItemInt.md)|Définit le texte d'un contrôle avec la chaîne qui représente une valeur entière.|  
|[CWnd::SetDlgItemText](../Topic/CWnd::SetDlgItemText.md)|Définit la légende ou le texte d'un contrôle dans la boîte de dialogue spécifiée.|  
|[CWnd::SetFocus](../Topic/CWnd::SetFocus.md)|Revendique le focus d'entrée.|  
|[CWnd::SetFont](../Topic/CWnd::SetFont.md)|Définit la police actuelle.|  
|[CWnd::SetForegroundWindow](../Topic/CWnd::SetForegroundWindow.md)|Place le thread créé par la fenêtre au premier plan et active la fenêtre.|  
|[CWnd::SetIcon](../Topic/CWnd::SetIcon.md)|Définit le handle avec une icône spécifique.|  
|[CWnd::SetLayeredWindowAttributes](../Topic/CWnd::SetLayeredWindowAttributes.md)|Définit la clé de couleur d'opacité et de transparence d'une fenêtre superposée.|  
|[CWnd::SetMenu](../Topic/CWnd::SetMenu.md)|Définit le menu avec le menu spécifié.|  
|[CWnd::SetOwner](../Topic/CWnd::SetOwner.md)|Modifie le propriétaire d'un `CWnd`.|  
|[CWnd::SetParent](../Topic/CWnd::SetParent.md)|Modifie la fenêtre parente.|  
|[CWnd::SetProperty](../Topic/CWnd::SetProperty.md)|Définit une propriété de contrôle ActiveX.|  
|[CWnd::SetRedraw](../Topic/CWnd::SetRedraw.md)|Autorise ou empêche le redessinage des modifications dans `CWnd`.|  
|[CWnd::SetScrollInfo](../Topic/CWnd::SetScrollInfo.md)|Définit les informations sur la barre de défilement.|  
|[CWnd::SetScrollPos](../Topic/CWnd::SetScrollPos.md)|Définit la position actuelle d'une case de défilement et, si elle est spécifiée, redessine la barre de défilement en fonction de la nouvelle position.|  
|[CWnd::SetScrollRange](../Topic/CWnd::SetScrollRange.md)|Définit les valeurs de position minimale et maximale de la barre de défilement donnée.|  
|[CWnd::SetTimer](../Topic/CWnd::SetTimer.md)|Installe une horloge système qui envoie un message [WM\_TIMER](../Topic/CWnd::OnTimer.md) quand il est déclenché.|  
|[CWnd::SetWindowContextHelpId](../Topic/CWnd::SetWindowContextHelpId.md)|Définit l'identificateur de contexte d'aide.|  
|[CWnd::SetWindowPlacement](../Topic/CWnd::SetWindowPlacement.md)|Définit l'état d'affichage et les positions normale \(restaurée\), réduite et agrandie d'une fenêtre.|  
|[CWnd::SetWindowPos](../Topic/CWnd::SetWindowPos.md)|Modifie la taille, la position et l'agencement des fenêtres enfants, indépendantes et de niveau supérieur.|  
|[CWnd::SetWindowRgn](../Topic/CWnd::SetWindowRgn.md)|Définit la région d'une fenêtre.|  
|[CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)|Définit le texte de la fenêtre ou le titre de la légende \(le cas échéant\) avec le texte spécifié.|  
|[CWnd::ShowCaret](../Topic/CWnd::ShowCaret.md)|Affiche le caret à l'écran à sa position actuelle.  Une fois affiché, le caret se met à clignoter automatiquement.|  
|[CWnd::ShowOwnedPopups](../Topic/CWnd::ShowOwnedPopups.md)|Affiche ou masque toutes les fenêtres indépendantes qui appartiennent à la fenêtre.|  
|[CWnd::ShowScrollBar](../Topic/CWnd::ShowScrollBar.md)|Affiche ou masque une barre de défilement.|  
|[CWnd::ShowWindow](../Topic/CWnd::ShowWindow.md)|Affiche ou masque la fenêtre.|  
|[CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md)|Attache un contrôle Windows à un objet `CWnd` et fait acheminer les messages via la table des messages de `CWnd`.|  
|[CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md)|Attache un fenêtre à un objet `CWnd` et fait acheminer les messages via la table des messages de `CWnd`.|  
|[CWnd::UnlockWindowUpdate](../Topic/CWnd::UnlockWindowUpdate.md)|Déverrouille une fenêtre qui était verrouillée avec `CWnd::LockWindowUpdate`.|  
|[CWnd::UnsubclassWindow](../Topic/CWnd::UnsubclassWindow.md)|Détache une fenêtre d'un objet `CWnd` .|  
|[CWnd::UpdateData](../Topic/CWnd::UpdateData.md)|Initialise ou récupère les données d'une boîte de dialogue.|  
|[CWnd::UpdateDialogControls](../Topic/CWnd::UpdateDialogControls.md)|Appelle à mettre à jour l'état de boutons et autres contrôles de boîte de dialogue.|  
|[CWnd::UpdateLayeredWindow](../Topic/CWnd::UpdateLayeredWindow.md)|Met à jour la position, la taille, la forme, le contenu et la transparence d'une fenêtre superposée.|  
|[CWnd::UpdateWindow](../Topic/CWnd::UpdateWindow.md)|Met à jour la zone cliente.|  
|[CWnd::ValidateRect](../Topic/CWnd::ValidateRect.md)|Valide la zone cliente dans le rectangle donné en supprimant le rectangle de la région de mise à jour actuelle.|  
|[CWnd::ValidateRgn](../Topic/CWnd::ValidateRgn.md)|Valide la zone cliente dans la région donnée en supprimant la région de la région de mise à jour actuelle.|  
|[CWnd::WindowFromPoint](../Topic/CWnd::WindowFromPoint.md)|Identifie la fenêtre qui contient le point donné.|  
|[CWnd::WinHelp](../Topic/CWnd::WinHelp.md)|Appelé pour lancer l'application WinHelp.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CWnd::Default](../Topic/CWnd::Default.md)|Appelle la procédure de fenêtre par défaut, qui assure le traitement par défaut des messages de fenêtre qu'une application ne traite pas.|  
|[CWnd::DefWindowProc](../Topic/CWnd::DefWindowProc.md)|Appelle la procédure de fenêtre par défaut, qui assure le traitement par défaut des messages de fenêtre qu'une application ne traite pas.|  
|[CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)|Pour l'échange et la validation de données de boîte de dialogue.  Appelé par `UpdateData`.|  
|[CWnd::GetCurrentMessage](../Topic/CWnd::GetCurrentMessage.md)|Retourne un pointeur vers le message actuellement traité par cette fenêtre.  Doit être appelé uniquement quand il se trouve dans une fonction membre de gestionnaire de messages `On`*Message*.|  
|[CWnd::InitDynamicLayout](../Topic/CWnd::InitDynamicLayout.md)|Appelé par l'infrastructure pour initialiser la disposition dynamique pour la fenêtre.|  
|[CWnd::LoadDynamicLayoutResource](../Topic/CWnd::LoadDynamicLayoutResource.md)|Charge les informations de disposition dynamique à partir du fichier de ressources.|  
|[CWnd::OnActivate](../Topic/CWnd::OnActivate.md)|Appelé pendant l'activation ou la désactivation de `CWnd`.|  
|[CWnd::OnActivateApp](../Topic/CWnd::OnActivateApp.md)|Appelé quand l'application est sur le point d'être activée ou désactivée.|  
|[CWnd::OnAppCommand](../Topic/CWnd::OnAppCommand.md)|Appelé quand l'utilisateur génère un événement de commande d'application.|  
|[CWnd::OnAskCbFormatName](../Topic/CWnd::OnAskCbFormatName.md)|Appelé par une application de visualisation de Presse\-papiers quand un propriétaire de Presse\-papiers affiche le contenu du Presse\-papiers.|  
|[CWnd::OnCancelMode](../Topic/CWnd::OnCancelMode.md)|Appelé pour permettre à `CWnd` d'annuler les modes internes, tels que la capture de la souris.|  
|[CWnd::OnCaptureChanged](../Topic/CWnd::OnCaptureChanged.md)|Envoie un message à la fenêtre qui perd la capture de la souris.|  
|[CWnd::OnChangeCbChain](../Topic/CWnd::OnChangeCbChain.md)|Signale qu'une fenêtre spécifiée va être supprimée de la chaîne.|  
|[CWnd::OnChangeUIState](../Topic/CWnd::OnChangeUIState.md)|Appelé quand l'état de l'interface utilisateur \(IU\) doit être modifié.|  
|[CWnd::OnChar](../Topic/CWnd::OnChar.md)|Appelé quand une séquence de touches est traduite en caractère non système.|  
|[CWnd::OnCharToItem](../Topic/CWnd::OnCharToItem.md)|Appelé par une zone de liste enfant avec le style [LBS\_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) en réponse à un message [WM\_CHAR](../Topic/CWnd::OnChar.md).|  
|[CWnd::OnChildActivate](../Topic/CWnd::OnChildActivate.md)|Appelé pour des fenêtres enfants d'interface multidocument \(MDI\) chaque fois que la taille ou la position de `CWnd` change ou que `CWnd` est activé.|  
|[CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)|Appelé par une fenêtre parente pour offrir à un contrôle de notification la possibilité de répondre à une notification de contrôle.|  
|[CWnd::OnClipboardUpdate](../Topic/CWnd::OnClipboardUpdate.md)|Envoyé quand le contenu du Presse\-papiers a changé.|  
|[CWnd::OnClose](../Topic/CWnd::OnClose.md)|Appelé pour signaler que `CWnd` doit être fermé.|  
|[CWnd::OnColorizationColorChanged](../Topic/CWnd::OnColorizationColorChanged.md)|Appelé quand la stratégie de rendu de la zone non cliente a changé.|  
|[CWnd::OnCommand](../Topic/CWnd::OnCommand.md)|Appelé quand l'utilisateur sélectionne une commande.|  
|[CWnd::OnCompacting](../Topic/CWnd::OnCompacting.md)|Appelé quand Windows détecte que la mémoire système est insuffisante.|  
|[CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)|Appelé pour déterminer la position relative d'un nouvel élément dans une zone de liste modifiable ou une zone de liste enfant triée en mode owner\-draw.|  
|[CWnd::OnCompositionChanged](../Topic/CWnd::OnCompositionChanged.md)|Appelé pour toutes les fenêtres de niveau supérieur quand la composition du Gestionnaire de fenêtrage est activée ou désactivée.|  
|[CWnd::OnContextMenu](../Topic/CWnd::OnContextMenu.md)|Appelé quand l'utilisateur clique dans la fenêtre avec le bouton droit de la souris.|  
|[CWnd::OnCopyData](../Topic/CWnd::OnCopyData.md)|Copie les données d'une application vers une autre.|  
|[CWnd::OnCreate](../Topic/CWnd::OnCreate.md)|Appelé dans le cadre de la création d'une fenêtre.|  
|[CWnd::OnCtlColor](../Topic/CWnd::OnCtlColor.md)|Appelé si `CWnd` est le parent d'un contrôle qui est sur le point d'être dessiné.|  
|[CWnd::OnDeadChar](../Topic/CWnd::OnDeadChar.md)|Appelé quand une séquence de touches est traduite en caractère de modificateur non système \(tel qu'un accent\).|  
|[CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)|Appelé quand une zone de liste ou une zone de liste modifiable enfant en mode owner\-draw est détruite ou que des éléments sont supprimés du contrôle.|  
|[CWnd::OnDestroy](../Topic/CWnd::OnDestroy.md)|Appelé quand `CWnd` va être détruit.|  
|[CWnd::OnDestroyClipboard](../Topic/CWnd::OnDestroyClipboard.md)|Appelé quand le Presse\-papiers est vidé via un appel à la fonction [EmptyClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649037) de Windows.|  
|[CWnd::OnDeviceChange](../Topic/CWnd::OnDeviceChange.md)|Avertit une application ou un pilote de périphérique que la configuration matérielle d'un périphérique ou de l'ordinateur a été modifiée.|  
|[CWnd::OnDevModeChange](../Topic/CWnd::OnDevModeChange.md)|Appelé pour toutes les fenêtres de niveau supérieur quand l'utilisateur modifie les paramètres de mode de périphérique.|  
|[CWnd::OnDrawClipboard](../Topic/CWnd::OnDrawClipboard.md)|Appelé quand le contenu du Presse\-papiers change.|  
|[CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)|Appelé quand un aspect visuel d'un contrôle enfant de bouton, zone de liste modifiable, zone de liste ou menu en mode owner\-draw doit être dessiné.|  
|[CWnd::OnDropFiles](../Topic/CWnd::OnDropFiles.md)|Appelé quand l'utilisateur relâche le bouton gauche de la souris dans une fenêtre qui s'est inscrite en tant que destinataire des fichiers déposés.|  
|[CWnd::OnEnable](../Topic/CWnd::OnEnable.md)|Appelé quand `CWnd` est activé ou désactivé.|  
|[CWnd::OnEndSession](../Topic/CWnd::OnEndSession.md)|Appelé quand la session prend fin.|  
|[CWnd::OnEnterIdle](../Topic/CWnd::OnEnterIdle.md)|Appelé pour informer la procédure de fenêtre principale d'une application qu'une boîte de dialogue modale ou un menu entre dans un état inactif.|  
|[CWnd::OnEnterMenuLoop](../Topic/CWnd::OnEnterMenuLoop.md)|Appelé lors de l'entrée dans une boucle modale de menu.|  
|[CWnd::OnEnterSizeMove](../Topic/CWnd::OnEnterSizeMove.md)|Appelé après l'entrée de la fenêtre affectée dans une boucle modale de déplacement ou de dimensionnement.|  
|[CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md)|Appelé quand l'arrière\-plan de la fenêtre doit être effacé.|  
|[CWnd::OnExitMenuLoop](../Topic/CWnd::OnExitMenuLoop.md)|Appelé lors de la sortie d'une boucle modale de menu.|  
|[CWnd::OnExitSizeMove](../Topic/CWnd::OnExitSizeMove.md)|Appelé après la sortie de la fenêtre affectée d'une boucle modale de déplacement ou de dimensionnement.|  
|[CWnd::OnFontChange](../Topic/CWnd::OnFontChange.md)|Appelé quand le pool de ressources de police change.|  
|[CWnd::OnGetDlgCode](../Topic/CWnd::OnGetDlgCode.md)|Appelé pour un contrôle afin de lui permettre de traiter lui\-même une entrée de touche de direction et de touche TAB.|  
|[CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)|Appelé chaque fois que Windows a besoin de connaître la position ou les dimensions agrandies ou la taille de suivi minimale ou maximale.|  
|[CWnd::OnHelpInfo](../Topic/CWnd::OnHelpInfo.md)|Appelé par l'infrastructure quand l'utilisateur appuie sur la touche F1.|  
|[CWnd::OnHotKey](../Topic/CWnd::OnHotKey.md)|Appelé quand l'utilisateur appuie sur une touche d'accès rapide à l'échelle du système.|  
|[CWnd::OnHScroll](../Topic/CWnd::OnHScroll.md)|Appelé quand l'utilisateur clique sur la barre de défilement horizontale de `CWnd`.|  
|[CWnd::OnHScrollClipboard](../Topic/CWnd::OnHScrollClipboard.md)|Appelé quand un propriétaire de Presse\-papiers doit faire défiler l'image du Presse\-papiers, invalider la section appropriée et mettre à jour les valeurs de la barre de défilement.|  
|[CWnd::OnIconEraseBkgnd](../Topic/CWnd::OnIconEraseBkgnd.md)|Appelé quand `CWnd` est réduit \(sous forme d'icône\) et que l'arrière\-plan de l'icône doit être rempli avant de peindre l'icône.|  
|[CWnd::OnInitMenu](../Topic/CWnd::OnInitMenu.md)|Appelé quand un menu va devenir actif.|  
|[CWnd::OnInitMenuPopup](../Topic/CWnd::OnInitMenuPopup.md)|Appelé quand un menu contextuel va devenir actif.|  
|[CWnd::OnInputDeviceChange](../Topic/CWnd::OnInputDeviceChange.md)|Appelé quand un périphérique d'E\/S est ajouté ou supprimé du système.|  
|[CWnd::OnInputLangChange](../Topic/CWnd::OnInputLangChange.md)|Appelé après la modification du langage d'entrée d'une application.|  
|[CWnd::OnInputLangChangeRequest](../Topic/CWnd::OnInputLangChangeRequest.md)|Appelé quand l'utilisateur choisit un nouveau langage d'entrée.|  
|[CWnd::OnKeyDown](../Topic/CWnd::OnKeyDown.md)|Appelé quand l'utilisateur appuie sur une touche non système.|  
|[CWnd::OnKeyUp](../Topic/CWnd::OnKeyUp.md)|Appelé quand l'utilisateur relâche une touche non système.|  
|[CWnd::OnKillFocus](../Topic/CWnd::OnKillFocus.md)|Appelé juste avant que `CWnd` perde le focus d'entrée.|  
|[CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton gauche de la souris.|  
|[CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton gauche de la souris.|  
|[CWnd::OnLButtonUp](../Topic/CWnd::OnLButtonUp.md)|Appelé quand l'utilisateur relâche le bouton gauche de la souris.|  
|[CWnd::OnMButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton central de la souris.|  
|[CWnd::OnMButtonDown](../Topic/CWnd::OnMButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton central de la souris.|  
|[CWnd::OnMButtonUp](../Topic/CWnd::OnMButtonUp.md)|Appelé quand l'utilisateur relâche le bouton central de la souris.|  
|[CWnd::OnMDIActivate](../Topic/CWnd::OnMDIActivate.md)|Appelé quand une fenêtre enfant MDI est activée ou désactivée.|  
|[CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)|Appelé pour une zone de liste modifiable, une zone de liste ou un élément de menu enfant en mode owner\-draw quand le contrôle est créé.  `CWnd` communique à Windows les dimensions du contrôle.|  
|[CWnd::OnMenuChar](../Topic/CWnd::OnMenuChar.md)|Appelé quand l'utilisateur appuie sur un caractère mnémonique de menu qui ne correspond à aucun des mnémoniques prédéfinis dans le menu actif.|  
|[CWnd::OnMenuDrag](../Topic/CWnd::OnMenuDrag.md)|Appelé quand l'utilisateur commence à faire glisser un élément de menu.|  
|[CWnd::OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md)|Appelé quand le curseur de la souris entre dans un élément de menu ou se déplace du centre de l'élément vers le haut ou le bas de l'élément.|  
|[CWnd::OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md)|Appelé quand l'utilisateur relâche le bouton droit de la souris et que le curseur se trouve sur un élément de menu.|  
|[CWnd::OnMenuSelect](../Topic/CWnd::OnMenuSelect.md)|Appelé quand l'utilisateur sélectionne un élément de menu.|  
|[CWnd::OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)|Appelé quand le curseur se trouve dans une fenêtre inactive et que l'utilisateur appuie sur un bouton de la souris.|  
|[CWnd::OnMouseHover](../Topic/CWnd::OnMouseHover.md)|Appelé quand le curseur pointe sur la zone cliente de la fenêtre pendant la période spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md)|Appelé quand la fenêtre active est composée par le Gestionnaire de fenêtrage et que cette fenêtre est agrandie.|  
|[CWnd::OnMouseLeave](../Topic/CWnd::OnMouseLeave.md)|Appelé quand le curseur quitte la zone cliente de la fenêtre spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnMouseMove](../Topic/CWnd::OnMouseMove.md)|Appelé quand le curseur de la souris se déplace.|  
|[CWnd::OnMouseWheel](../Topic/CWnd::OnMouseWheel.md)|Appelé quand un utilisateur fait tourner la roulette de la souris.  Utilise la gestion des messages de Windows NT 4.0.|  
|[CWnd::OnMove](../Topic/CWnd::OnMove.md)|Appelé après un changement de position de `CWnd`.|  
|[CWnd::OnMoving](../Topic/CWnd::OnMoving.md)|Indique qu'un utilisateur déplace un objet `CWnd`.|  
|[CWnd::OnNcActivate](../Topic/CWnd::OnNcActivate.md)|Appelé quand la zone non cliente doit être modifiée pour indiquer un état actif ou inactif.|  
|[CWnd::OnNcCalcSize](../Topic/CWnd::OnNcCalcSize.md)|Appelé quand la taille et la position de la zone client doivent être calculées.|  
|[CWnd::OnNcCreate](../Topic/CWnd::OnNcCreate.md)|Appelé avant [OnCreate](../Topic/CWnd::OnCreate.md) pendant la création de la zone non cliente.|  
|[CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)|Appelé quand la zone non cliente va être détruite.|  
|[CWnd::OnNcHitTest](../Topic/CWnd::OnNcHitTest.md)|Appelé par Windows chaque fois que la souris est déplacée si `CWnd` contient le curseur ou a capturé l'entrée de souris avec `SetCapture`.|  
|[CWnd::OnNcLButtonDblClk](../Topic/CWnd::OnNcLButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcLButtonDown](../Topic/CWnd::OnNcLButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcLButtonUp](../Topic/CWnd::OnNcLButtonUp.md)|Appelé quand l'utilisateur relâche le bouton gauche de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonDblClk](../Topic/CWnd::OnNcMButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonDown](../Topic/CWnd::OnNcMButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMButtonUp](../Topic/CWnd::OnNcMButtonUp.md)|Appelé quand l'utilisateur relâche le bouton central de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcMouseHover](../Topic/CWnd::OnNcMouseHover.md)|Appelé quand le curseur pointe sur la zone non cliente de la fenêtre pendant la période spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseLeave](../Topic/CWnd::OnNcMouseLeave.md)|L'infrastructure appelle cette fonction membre quand le curseur quitte la zone non cliente de la fenêtre spécifiée dans un appel antérieur à [TrackMouseEvent](http://msdn.microsoft.com/library/windows/desktop/ms646265).|  
|[CWnd::OnNcMouseMove](../Topic/CWnd::OnNcMouseMove.md)|Appelé quand le curseur est déplacé dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcPaint](../Topic/CWnd::OnNcPaint.md)|Appelé quand la zone non cliente doit être peinte.|  
|[CWnd::OnNcRButtonDblClk](../Topic/CWnd::OnNcRButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRButtonDown](../Topic/CWnd::OnNcRButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRButtonUp](../Topic/CWnd::OnNcRButtonUp.md)|Appelé quand l'utilisateur relâche le bouton droit de la souris pendant que le curseur se trouve dans une zone non cliente de `CWnd`.|  
|[CWnd::OnNcRenderingChanged](../Topic/CWnd::OnNcRenderingChanged.md)|Appelé quand la stratégie de rendu de la zone non cliente a changé.|  
|[CWnd::OnNcXButtonDblClk](../Topic/CWnd::OnNcXButtonDblClk.md)|Appelé quand l'utilisateur double\-clique sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone non cliente d'une fenêtre.|  
|[CWnd::OnNcXButtonDown](../Topic/CWnd::OnNcXButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton XBUTTON1 ou XBUTTON2 de la souris pendant que le curseur se trouve dans la zone non cliente d'une fenêtre.|  
|[CWnd::OnNcXButtonUp](../Topic/CWnd::OnNcXButtonUp.md)|Appelé quand l'utilisateur relâche le bouton XBUTTON1 ou XBUTTON2 de la souris pendant que le curseur se trouve dans la zone non cliente d'une fenêtre.|  
|[CWnd::OnNextMenu](../Topic/CWnd::OnNextMenu.md)|Appelé quand la touche de direction droite ou gauche est utilisée pour basculer entre la barre de menus et le menu système.|  
|[CWnd::OnNotify](../Topic/CWnd::OnNotify.md)|Appelé par l'infrastructure pour informer une fenêtre parente qu'un événement s'est produit dans l'un de ses contrôles ou que le contrôle a besoin d'informations.|  
|[CWnd::OnNotifyFormat](../Topic/CWnd::OnNotifyFormat.md)|Appelé pour déterminer si la fenêtre active accepte les structures ANSI ou Unicode dans le message de notification WM\_NOTIFY.|  
|[CWnd::OnPaint](../Topic/CWnd::OnPaint.md)|Appelé pour repeindre une partie de la fenêtre.|  
|[CWnd::OnPaintClipboard](../Topic/CWnd::OnPaintClipboard.md)|Appelé quand la zone cliente de la visionneuse de Presse\-papiers doit être repeinte.|  
|[CWnd::OnPaletteChanged](../Topic/CWnd::OnPaletteChanged.md)|Appelé pour permettre aux fenêtres qui utilisent une palette de couleurs de réaliser leurs palettes logiques et de mettre à jour leurs zones clientes.|  
|[CWnd::OnPaletteIsChanging](../Topic/CWnd::OnPaletteIsChanging.md)|Informe les autres applications qu'une application va réaliser sa palette logique.|  
|[CWnd::OnParentNotify](../Topic/CWnd::OnParentNotify.md)|Appelé quand une fenêtre enfant est créée ou détruite ou quand l'utilisateur clique avec un bouton de la souris pendant que le curseur se trouve dans la fenêtre enfant.|  
|[CWnd::OnPowerBroadcast](../Topic/CWnd::OnPowerBroadcast.md)|Appelé quand un événement de gestion de l'alimentation se produit.|  
|[CWnd::OnQueryDragIcon](../Topic/CWnd::OnQueryDragIcon.md)|Appelé quand un `CWnd` réduit \(sous forme d'icône\) est sur le point d'être déplacé par l'utilisateur.|  
|[CWnd::OnQueryEndSession](../Topic/CWnd::OnQueryEndSession.md)|Appelé quand l'utilisateur choisit de mettre fin à la session Windows.|  
|[CWnd::OnQueryNewPalette](../Topic/CWnd::OnQueryNewPalette.md)|Informe `CWnd` qu'il va recevoir le focus d'entrée.|  
|[CWnd::OnQueryOpen](../Topic/CWnd::OnQueryOpen.md)|Appelé quand `CWnd` est une icône et que l'utilisateur demande à ce qu'elle soit ouverte.|  
|[CWnd::OnQueryUIState](../Topic/CWnd::OnQueryUIState.md)|Appelé pour récupérer l'état de l'interface utilisateur \(IU\) pour une fenêtre.|  
|[CWnd::OnRawInput](../Topic/CWnd::OnRawInput.md)|Appelé quand la fenêtre active obtient une entrée brute.|  
|[CWnd::OnRButtonDblClk](../Topic/CWnd::OnRButtonDblClk.md)|Appelé quand l'utilisateur double\-clique avec le bouton droit de la souris.|  
|[CWnd::OnRButtonDown](../Topic/CWnd::OnRButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton droit de la souris.|  
|[CWnd::OnRButtonUp](../Topic/CWnd::OnRButtonUp.md)|Appelé quand l'utilisateur relâche le bouton droit de la souris.|  
|[CWnd::OnRenderAllFormats](../Topic/CWnd::OnRenderAllFormats.md)|Appelé quand l'application propriétaire va être détruite et qu'elle doit restituer tous ses formats.|  
|[CWnd::OnRenderFormat](../Topic/CWnd::OnRenderFormat.md)|Appelé pour le propriétaire du Presse\-papiers quand un format particulier avec rendu retardé doit être restitué.|  
|[CWnd::OnSessionChange](../Topic/CWnd::OnSessionChange.md)|Appelé pour avertir une application d'un changement d'état de session.|  
|[CWnd::OnSetCursor](../Topic/CWnd::OnSetCursor.md)|Appelé si l'entrée de la souris n'est pas capturée et que la souris entraîne le déplacement du curseur dans une fenêtre.|  
|[CWnd::OnSetFocus](../Topic/CWnd::OnSetFocus.md)|Appelé après que `CWnd` a obtenu le focus d'entrée.|  
|[CWnd::OnSettingChange](../Topic/CWnd::OnSettingChange.md)|Appelé quand la fonction Win32 `SystemParametersInfo` modifie un paramètre à l'échelle du système.|  
|[CWnd::OnShowWindow](../Topic/CWnd::OnShowWindow.md)|Appelé quand `CWnd` doit être masqué ou affiché.|  
|[CWnd::OnSize](../Topic/CWnd::OnSize.md)|Appelé après que la taille de `CWnd` a changé.|  
|[CWnd::OnSizeClipboard](../Topic/CWnd::OnSizeClipboard.md)|Appelé quand la taille de la zone cliente de la fenêtre de visualisation de Presse\-papiers a changé.|  
|[CWnd::OnSizing](../Topic/CWnd::OnSizing.md)|Indique que l'utilisateur redimensionne le rectangle.|  
|[CWnd::OnSpoolerStatus](../Topic/CWnd::OnSpoolerStatus.md)|Appelé depuis le Gestionnaire d'impression chaque fois qu'un travail est ajouté ou supprimé dans la fille d'attente du Gestionnaire d'impression.|  
|[CWnd::OnStyleChanged](../Topic/CWnd::OnStyleChanged.md)|Indique que la fonction [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) de Windows a modifié un ou plusieurs styles de la fenêtre.|  
|[CWnd::OnStyleChanging](../Topic/CWnd::OnStyleChanging.md)|Indique que la fonction [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) de Windows va modifier un ou plusieurs styles de la fenêtre.|  
|[CWnd::OnSysChar](../Topic/CWnd::OnSysChar.md)|Appelé quand une séquence de touches est traduite en caractère système.|  
|[CWnd::OnSysColorChange](../Topic/CWnd::OnSysColorChange.md)|Appelé pour toutes les fenêtres de niveau supérieur quand une modification est apportée au paramètre de couleur système.|  
|[CWnd::OnSysCommand](../Topic/CWnd::OnSysCommand.md)|Appelé quand l'utilisateur sélectionne une commande dans le menu Système ou qu'il sélectionne le bouton Agrandir ou Réduire.|  
|[CWnd::OnSysDeadChar](../Topic/CWnd::OnSysDeadChar.md)|Appelé quand une séquence de touches est traduite en caractère de modificateur système \(tel qu'un accent\).|  
|[CWnd::OnSysKeyDown](../Topic/CWnd::OnSysKeyDown.md)|Appelé quand l'utilisateur maintient la touche ALT enfoncée, puis qu'il appuie sur une autre touche.|  
|[CWnd::OnSysKeyUp](../Topic/CWnd::OnSysKeyUp.md)|Appelé quand l'utilisateur relâche une touche sur laquelle il avait appuyé tout en ayant maintenu la touche ALT enfoncée.|  
|[CWnd::OnTCard](../Topic/CWnd::OnTCard.md)|Appelé quand l'utilisateur clique sur un bouton autorisé.|  
|[CWnd::OnTimeChange](../Topic/CWnd::OnTimeChange.md)|Appelé pour toutes les fenêtres de niveau supérieur après un changement d'heure système.|  
|[CWnd::OnTimer](../Topic/CWnd::OnTimer.md)|Appelé après chaque intervalle spécifié dans [SetTimer](../Topic/CWnd::SetTimer.md).|  
|[CWnd::OnTouchInput](../Topic/CWnd::OnTouchInput.md)|Traite une entrée unique de l'interface tactile Windows.|  
|[CWnd::OnTouchInputs](../Topic/CWnd::OnTouchInputs.md)|Traite les entrées de l'interface tactile Windows.|  
|[CWnd::OnUniChar](../Topic/CWnd::OnUniChar.md)|Appelé quand un utilisateur appuie sur une touche.  Autrement dit, la fenêtre active a le focus clavier et un message [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) est traduit par la fonction [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955).|  
|[CWnd::OnUnInitMenuPopup](../Topic/CWnd::OnUnInitMenuPopup.md)|Appelé quand un menu ou sous\-menu déroulant a été détruit.|  
|[CWnd::OnUpdateUIState](../Topic/CWnd::OnUpdateUIState.md)|Appelé pour modifier l'état de l'interface utilisateur pour la fenêtre spécifiée et toutes ses fenêtres enfants.|  
|[CWnd::OnUserChanged](../Topic/CWnd::OnUserChanged.md)|Appelé après la connexion ou la déconnexion de l'utilisateur.|  
|[CWnd::OnVKeyToItem](../Topic/CWnd::OnVKeyToItem.md)|Appelé par une zone de liste détenue par `CWnd` en réponse à un message [WM\_KEYDOWN](../Topic/CWnd::OnKeyDown.md).|  
|[CWnd::OnVScroll](../Topic/CWnd::OnVScroll.md)|Appelé quand l'utilisateur clique sur la barre de défilement verticale de la fenêtre.|  
|[CWnd::OnVScrollClipboard](../Topic/CWnd::OnVScrollClipboard.md)|Appelé quand le propriétaire doit faire défiler l'image du Presse\-papiers, invalider la section appropriée et mettre à jour les valeurs de la barre de défilement.|  
|[CWnd::OnWindowPosChanged](../Topic/CWnd::OnWindowPosChanged.md)|Appelé quand la taille, la position ou l'ordre de plan a changé suite à un appel à [SetWindowPos](../Topic/CWnd::SetWindowPos.md) ou à une autre fonction de gestion de fenêtrage.|  
|[CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)|Appelé quand la taille, la position ou l'ordre de plan va changer suite à un appel à [SetWindowPos](../Topic/CWnd::SetWindowPos.md) ou à une autre fonction de gestion de fenêtrage.|  
|[CWnd::OnWinIniChange](../Topic/CWnd::OnWinIniChange.md)|Appelé pour toutes les fenêtres de niveau supérieur après que le fichier d'initialisation de Windows, WIN. INI, a été modifié.|  
|[CWnd::OnWndMsg](../Topic/CWnd::OnWndMsg.md)|Indique si un message Windows a été traité.|  
|[CWnd::OnXButtonDblClk](../Topic/CWnd::OnXButtonDblClk.md)|Appelé quand l'utilisateur double\-clique sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d'une fenêtre.|  
|[CWnd::OnXButtonDown](../Topic/CWnd::OnXButtonDown.md)|Appelé quand l'utilisateur appuie sur le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d'une fenêtre.|  
|[CWnd::OnXButtonUp](../Topic/CWnd::OnXButtonUp.md)|Appelé quand l'utilisateur relâche le bouton XBUTTON1 ou XBUTTON2 pendant que le curseur se trouve dans la zone cliente d'une fenêtre.|  
|[CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)|Cette fonction virtuelle est appelée par la fonction [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md) par défaut après que la fenêtre a été détruite.|  
|[CWnd::ReflectChildNotify](../Topic/CWnd::ReflectChildNotify.md)|Fonction d'assistance qui reflète un message à sa source.|  
|[CWnd::ReflectLastMsg](../Topic/CWnd::ReflectLastMsg.md)|Reflète le dernier message à la fenêtre enfant.|  
|[CWnd::ResizeDynamicLayout](../Topic/CWnd::ResizeDynamicLayout.md)|Appelé par l'infrastructure quand la taille de fenêtre change pour ajuster la disposition des fenêtres enfants, si la disposition dynamique est activée pour la fenêtre.|  
|[CWnd::WindowProc](../Topic/CWnd::WindowProc.md)|Fournit une procédure de fenêtre pour un `CWnd`.  Par défaut, les messages sont distribués via la table des messages|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWnd::operator HWND](../Topic/CWnd::operator%20HWND.md)|Appelé pour obtenir un handle de fenêtre.|  
|[CWnd::operator \!\=](../Topic/CWnd::operator%20!=.md)|Détermine si une fenêtre n'est pas identique à la fenêtre dont le handle est [m\_hWnd](../Topic/CWnd::m_hWnd.md).|  
|[CWnd::operator \=\=](../Topic/CWnd::operator%20==.md)|Détermine si une fenêtre est identique à la fenêtre dont le handle est [m\_hWnd](../Topic/CWnd::m_hWnd.md).|  
  
### Membres de données publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWnd::m\_hWnd](../Topic/CWnd::m_hWnd.md)|Indique le `HWND` attaché à ce `CWnd`.|  
  
## Notes  
 Un objet `CWnd` est distinct d'une fenêtre Windows, mais les deux sont étroitement liés.  Un objet `CWnd` est créé ou détruit par le constructeur et destructeur `CWnd`.  En revanche, une fenêtre Windows est une structure de données interne à Windows qui est créée par une fonction membre **Create** et détruite par le destructeur virtuel `CWnd`.  La fonction [DestroyWindow](../Topic/CWnd::DestroyWindow.md) détruit la fenêtre Windows sans détruire l'objet.  
  
 La classe `CWnd` et le mécanisme de table des messages masquent la fonction **WndProc**.  Les messages de notification Windows entrants sont automatiquement acheminés via la table des messages vers les fonctions membres **On***Message* `CWnd` appropriées.  Vous devez substituer une fonction membre **On***Message* pour traiter le message particulier d'un membre dans vos classes dérivées.  
  
 La classe `CWnd` vous permet aussi de créer une fenêtre enfant Windows pour votre application.  Faites dériver une classe de `CWnd`, puis ajoutez des variables membres à la classe dérivée pour stocker les données propres à votre application.  Implémentez des fonctions membres de gestionnaire de messages et une table des messages dans la classe dérivée pour préciser ce qu'il advient quand des messages sont dirigés vers la fenêtre.  
  
 Une fenêtre enfant se crée en deux étapes.  Pour commencer, appelez le constructeur `CWnd` pour construire l'objet `CWnd`, puis appelez la fonction membre [Create](../Topic/CWnd::Create.md) pour créer la fenêtre enfant et l'attacher à l'objet `CWnd`.  
  
 Quand l'utilisateur ferme votre fenêtre enfant, détruisez l'objet `CWnd` ou appelez la fonction membre `DestroyWindow` pour supprimer la fenêtre et détruire ses structures de données.  
  
 Dans la bibliothèque MFC \(Microsoft Foundation Class\), d'autres classes sont dérivées de `CWnd` pour fournir des types de fenêtres spécifiques.  Un grand nombre de ces classes, notamment [CFrameWnd](../../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md), [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md), [CView](../../mfc/reference/cview-class.md) et [CDialog](../../mfc/reference/cdialog-class.md), visent à être dérivées plus avant.  Les classes de contrôle dérivées de `CWnd`, telles que [CButton](../../mfc/reference/cbutton-class.md), peuvent être utilisées directement ou servir de base à une dérivation de classes supplémentaire.  
  
 Pour plus d'informations sur l'utilisation de `CWnd`, consultez [Fenêtres frame](../../mfc/frame-windows.md) et [Objets fenêtres](../../mfc/window-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWnd`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)