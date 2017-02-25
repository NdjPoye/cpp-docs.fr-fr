---
title: "CWindow Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWindow"
  - "ATL::CWindow"
  - "CWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindow class"
ms.assetid: fefa00c8-f053-4bcf-87bc-dc84f5386683
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour manipuler une fenêtre.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CWindow  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindow::CWindow](../Topic/CWindow::CWindow.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindow::ArrangeIconicWindows](../Topic/CWindow::ArrangeIconicWindows.md)|Réorganise toutes les fenêtres enfants réduites.|  
|[CWindow::Attach](../Topic/CWindow::Attach.md)|Joint une fenêtre à l'objet d' `CWindow` .|  
|[CWindow::BeginPaint](../Topic/CWindow::BeginPaint.md)|Prépare la fenêtre pour la peinture.|  
|[CWindow::BringWindowToTop](../Topic/CWindow::BringWindowToTop.md)|Apporte la fenêtre en haut de l'ordre de plan.|  
|[CWindow::CenterWindow](../Topic/CWindow::CenterWindow.md)|Centre de la fenêtre sur une fenêtre donnée.|  
|[CWindow::ChangeClipboardChain](../Topic/CWindow::ChangeClipboardChain.md)|Supprime la fenêtre de la chaîne de presse\-papiers.|  
|[CWindow::CheckDlgButton](../Topic/CWindow::CheckDlgButton.md)|Change l'état d'activation du bouton spécifié.|  
|[CWindow::CheckRadioButton](../Topic/CWindow::CheckRadioButton.md)|Contrôle la case d'option spécifiée.|  
|[CWindow::ChildWindowFromPoint](../Topic/CWindow::ChildWindowFromPoint.md)|Extrait la fenêtre enfant contenant le point spécifié.|  
|[CWindow::ChildWindowFromPointEx](../Topic/CWindow::ChildWindowFromPointEx.md)|Récupère un type particulier de fenêtre enfant contenant le point spécifié.|  
|[CWindow::ClientToScreen](../Topic/CWindow::ClientToScreen.md)|Convertit les coordonnées clientes pour examiner les coordonnées.|  
|[CWindow::Create](../Topic/CWindow::Create.md)|Crée une fenêtre.|  
|[CWindow::CreateCaret](../Topic/CWindow::CreateCaret.md)|Crée un nouveau formulaire pour le signe insertion.|  
|[CWindow::CreateGrayCaret](../Topic/CWindow::CreateGrayCaret.md)|Crée un rectangle gris pour le signe insertion.|  
|[CWindow::CreateSolidCaret](../Topic/CWindow::CreateSolidCaret.md)|Crée un rectangle plein du signe insertion.|  
|[CWindow::DeferWindowPos](../Topic/CWindow::DeferWindowPos.md)|Met à jour la structure spécifiée de multiple\-fenêtre\- position de la fenêtre spécifiée.|  
|[CWindow::DestroyWindow](../Topic/CWindow::DestroyWindow.md)|Perd la fenêtre associé à l'objet d' `CWindow` .|  
|[CWindow::Detach](../Topic/CWindow::Detach.md)|Détache la fenêtre de l'objet d' `CWindow` .|  
|[CWindow::DlgDirList](../Topic/CWindow::DlgDirList.md)|Remplit la zone de liste de noms de tous les fichiers correspondant à un chemin d'accès ou un nom de fichier spécifié.|  
|[CWindow::DlgDirListComboBox](../Topic/CWindow::DlgDirListComboBox.md)|Remplit la zone de liste déroulante de noms de tous les fichiers correspondant à un chemin d'accès ou un nom de fichier spécifié.|  
|[CWindow::DlgDirSelect](../Topic/CWindow::DlgDirSelect.md)|Extrait la sélection actuelle d'une zone de liste.|  
|[CWindow::DlgDirSelectComboBox](../Topic/CWindow::DlgDirSelectComboBox.md)|Extrait la sélection actuelle d'une zone de liste déroulante.|  
|[CWindow::DragAcceptFiles](../Topic/CWindow::DragAcceptFiles.md)|S'inscrit si la fenêtre reçoit les fichiers déplacés.|  
|[CWindow::DrawMenuBar](../Topic/CWindow::DrawMenuBar.md)|Redessine la barre de menus de la fenêtre.|  
|[CWindow::EnableScrollBar](../Topic/CWindow::EnableScrollBar.md)|Active ou désactive les flèches de barre de défilement.|  
|[CWindow::EnableWindow](../Topic/CWindow::EnableWindow.md)|Active ou désactive l'entrée.|  
|[CWindow::EndPaint](../Topic/CWindow::EndPaint.md)|Marque la fin de la peinture.|  
|[CWindow::FlashWindow](../Topic/CWindow::FlashWindow.md)|Flashe la fenêtre une fois.|  
|[CWindow::GetClientRect](../Topic/CWindow::GetClientRect.md)|Récupère les coordonnées de la zone cliente.|  
|[CWindow::GetDC](../Topic/CWindow::GetDC.md)|Récupère un contexte de périphérique pour la zone cliente.|  
|[CWindow::GetDCEx](../Topic/CWindow::GetDCEx.md)|Récupère un contexte de périphérique pour la zone cliente et fournit des options de découpage.|  
|[CWindow::GetDescendantWindow](../Topic/CWindow::GetDescendantWindow.md)|Extrait la fenêtre enfant spécifiée.|  
|[CWindow::GetDlgControl](../Topic/CWindow::GetDlgControl.md)|Extrait une interface sur le contrôle spécifié.|  
|[CWindow::GetDlgCtrlID](../Topic/CWindow::GetDlgCtrlID.md)|Récupère l'identificateur de la fenêtre \(pour les fenêtres enfants uniquement\).|  
|[CWindow::GetDlgHost](../Topic/CWindow::GetDlgHost.md)|Extrait un pointeur vers une interface au conteneur d'hébergement de contrôle ATL.|  
|[CWindow::GetDlgItem](../Topic/CWindow::GetDlgItem.md)|Extrait la fenêtre enfant spécifiée.|  
|[CWindow::GetDlgItemInt](../Topic/CWindow::GetDlgItemInt.md)|Convertit le texte d'un contrôle à un entier.|  
|[CWindow::GetDlgItemText](../Topic/CWindow::GetDlgItemText.md)|Extrait le texte d'un contrôle.|  
|[CWindow::GetExStyle](../Topic/CWindow::GetExStyle.md)|Récupère les styles de fenêtre étendus.|  
|[CWindow::GetFont](../Topic/CWindow::GetFont.md)|Extrait la police actuelle de la fenêtre.|  
|[CWindow::GetHotKey](../Topic/CWindow::GetHotKey.md)|Détermine la touche d'accès rapide associée à la fenêtre.|  
|[CWindow::GetIcon](../Topic/CWindow::GetIcon.md)|Extrait la fenêtre grande ou la petite icône.|  
|[CWindow::GetLastActivePopup](../Topic/CWindow::GetLastActivePopup.md)|Extrait la fenêtre indépendante récemment active.|  
|[CWindow::GetMenu](../Topic/CWindow::GetMenu.md)|Récupère le menu de fenêtre.|  
|[CWindow::GetNextDlgGroupItem](../Topic/CWindow::GetNextDlgGroupItem.md)|Récupère le contrôle précédent ou suivant au sein d'un groupe de contrôles.|  
|[CWindow::GetNextDlgTabItem](../Topic/CWindow::GetNextDlgTabItem.md)|Récupère le contrôle précédent ou suivant ayant le style de **WS\_TABSTOP** .|  
|[CWindow::GetParent](../Topic/CWindow::GetParent.md)|Extrait la fenêtre parente immédiate.|  
|[CWindow::GetScrollInfo](../Topic/CWindow::GetScrollInfo.md)|Récupère les paramètres d'une barre de défilement.|  
|[CWindow::GetScrollPos](../Topic/CWindow::GetScrollPos.md)|Extrait la position de la case de défilement.|  
|[CWindow::GetScrollRange](../Topic/CWindow::GetScrollRange.md)|Récupère l'intervalle de barre de défilement.|  
|[CWindow::GetStyle](../Topic/CWindow::GetStyle.md)|Récupère les styles de fenêtre.|  
|[CWindow::GetSystemMenu](../Topic/CWindow::GetSystemMenu.md)|Crée une copie du menu système pour la modification.|  
|[CWindow::GetTopLevelParent](../Topic/CWindow::GetTopLevelParent.md)|Récupère le parent ou la fenêtre propriétaire de niveau supérieur.|  
|[CWindow::GetTopLevelWindow](../Topic/CWindow::GetTopLevelWindow.md)|Extrait la fenêtre propriétaire de niveau supérieur.|  
|[CWindow::GetTopWindow](../Topic/CWindow::GetTopWindow.md)|Extrait la fenêtre enfant de niveau supérieur.|  
|[CWindow::GetUpdateRect](../Topic/CWindow::GetUpdateRect.md)|Récupère les coordonnées du plus petit rectangle qui englobe complètement la zone de mise à jour.|  
|[CWindow::GetUpdateRgn](../Topic/CWindow::GetUpdateRgn.md)|Extrait la zone de mise à jour et la copie dans une région spécifiée.|  
|[CWindow::GetWindow](../Topic/CWindow::GetWindow.md)|Extrait la fenêtre spécifiée.|  
|[CWindow::GetWindowContextHelpId](../Topic/CWindow::GetWindowContextHelpId.md)|Récupère l'identificateur de contexte d'aide de la fenêtre.|  
|[CWindow::GetWindowDC](../Topic/CWindow::GetWindowDC.md)|Récupère un contexte de périphérique pour la fenêtre entière.|  
|[CWindow::GetWindowLong](../Topic/CWindow::GetWindowLong.md)|Récupère une valeur 32 bits à un offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::GetWindowLongPtr](../Topic/CWindow::GetWindowLongPtr.md)|Récupère des informations sur la fenêtre spécifiée, y compris une valeur à un offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::GetWindowPlacement](../Topic/CWindow::GetWindowPlacement.md)|Récupère l'état et les positions show.|  
|[CWindow::GetWindowProcessID](../Topic/CWindow::GetWindowProcessID.md)|Récupère l'identificateur de processus qui a créé la fenêtre.|  
|[CWindow::GetWindowRect](../Topic/CWindow::GetWindowRect.md)|Récupère les dimensions les englobant de la fenêtre.|  
|[CWindow::GetWindowRgn](../Topic/CWindow::GetWindowRgn.md)|Obtient une copie de la zone de la fenêtre d'une fenêtre.|  
|[CWindow::GetWindowText](../Topic/CWindow::GetWindowText.md)|Extrait le texte de la fenêtre.|  
|[CWindow::GetWindowTextLength](../Topic/CWindow::GetWindowTextLength.md)|Extrait la longueur du texte de la fenêtre.|  
|[CWindow::GetWindowThreadID](../Topic/CWindow::GetWindowThreadID.md)|Récupère l'identificateur du thread qui a créé la fenêtre spécifiée.|  
|[CWindow::GetWindowWord](../Topic/CWindow::GetWindowWord.md)|Récupère une valeur 16 bits à un offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::GotoDlgCtrl](../Topic/CWindow::GotoDlgCtrl.md)|Place le focus clavier à un contrôle dans la boîte de dialogue.|  
|[CWindow::HideCaret](../Topic/CWindow::HideCaret.md)|Masque le signe insertion.|  
|[CWindow::HiliteMenuItem](../Topic/CWindow::HiliteMenuItem.md)|Les surbrillances ou supprime la mise en surbrillance d'un élément de menu de niveau supérieur.|  
|[CWindow::Invalidate](../Topic/CWindow::Invalidate.md)|Invalide la zone cliente entière.|  
|[CWindow::InvalidateRect](../Topic/CWindow::InvalidateRect.md)|Invalide la zone cliente dans le rectangle spécifié.|  
|[CWindow::InvalidateRgn](../Topic/CWindow::InvalidateRgn.md)|Invalide la zone cliente dans la zone spécifiée.|  
|[CWindow::IsChild](../Topic/CWindow::IsChild.md)|Détermine si la fenêtre spécifiée est une fenêtre enfant.|  
|[CWindow::IsDialogMessage](../Topic/CWindow::IsDialogMessage.md)|Détermine si un message est prévu pour la boîte de dialogue spécifiée.|  
|[CWindow::IsDlgButtonChecked](../Topic/CWindow::IsDlgButtonChecked.md)|Détermine l'état d'activation du bouton.|  
|[CWindow::IsIconic](../Topic/CWindow::IsIconic.md)|Détermine si la fenêtre est réduite.|  
|[CWindow::IsParentDialog](../Topic/CWindow::IsParentDialog.md)|Détermine si la fenêtre parente d'un contrôle est une fenêtre de dialogue.|  
|[CWindow::IsWindow](../Topic/CWindow::IsWindow.md)|Détermine si le handle de fenêtre spécifiée identifie une fenêtre existante.|  
|[CWindow::IsWindowEnabled](../Topic/CWindow::IsWindowEnabled.md)|Détermine si la fenêtre est activée pour l'entrée.|  
|[CWindow::IsWindowUnicode](../Topic/CWindow::IsWindowUnicode.md)|Détermine si la fenêtre spécifiée est une fenêtre Unicode native.|  
|[CWindow::IsWindowVisible](../Topic/CWindow::IsWindowVisible.md)|Détermine l'état de visibilité de la fenêtre.|  
|[CWindow::IsZoomed](../Topic/CWindow::IsZoomed.md)|Détermine si la fenêtre est agrandie.|  
|[CWindow::KillTimer](../Topic/CWindow::KillTimer.md)|Détruit un événement de minuterie.|  
|[CWindow::LockWindowUpdate](../Topic/CWindow::LockWindowUpdate.md)|Les active ou désactive le dessin dans la fenêtre.|  
|[CWindow::MapWindowPoints](../Topic/CWindow::MapWindowPoints.md)|Convertit un jeu de points de l'espace de coordonnées de la fenêtre à l'espace de coordonnées d'une autre fenêtre.|  
|[CWindow::MessageBox](../Topic/CWindow::MessageBox.md)|Affiche une boîte de message.|  
|[CWindow::ModifyStyle](../Topic/CWindow::ModifyStyle.md)|Modifie les styles de fenêtre.|  
|[CWindow::ModifyStyleEx](../Topic/CWindow::ModifyStyleEx.md)|Modifie les styles de fenêtre étendus.|  
|[CWindow::MoveWindow](../Topic/CWindow::MoveWindow.md)|Modifie la taille et la position de la fenêtre.|  
|[CWindow::NextDlgCtrl](../Topic/CWindow::NextDlgCtrl.md)|Place le focus clavier au contrôle suivant dans la boîte de dialogue.|  
|[CWindow::OpenClipboard](../Topic/CWindow::OpenClipboard.md)|Ouvre le presse\-papiers.|  
|[CWindow::PostMessage](../Topic/CWindow::PostMessage.md)|Définit un message dans la file d'attente de messages associée au thread qui a créé la fenêtre.  Retourne la valeur sans attendre que le thread pour traiter le message.|  
|[CWindow::PrevDlgCtrl](../Topic/CWindow::PrevDlgCtrl.md)|Place le focus clavier au contrôle précédent dans la boîte de dialogue.|  
|[CWindow::Print](../Topic/CWindow::Print.md)|Les demandes ces la fenêtre sont dessinées dans un contexte spécifié de périphérique.|  
|[CWindow::PrintClient](../Topic/CWindow::PrintClient.md)|Les demandes ces la zone cliente de la fenêtre sont dessinées dans un contexte spécifié de périphérique.|  
|[CWindow::RedrawWindow](../Topic/CWindow::RedrawWindow.md)|Met à jour un rectangle ou une région spécifiée dans la zone cliente.|  
|[CWindow::ReleaseDC](../Topic/CWindow::ReleaseDC.md)|Libère un contexte de périphérique.|  
|[CWindow::ResizeClient](../Topic/CWindow::ResizeClient.md)|Redimensionne la fenêtre.|  
|[CWindow::ScreenToClient](../Topic/CWindow::ScreenToClient.md)|Coordonnées d'écran de convertis aux coordonnées clientes.|  
|[CWindow::ScrollWindow](../Topic/CWindow::ScrollWindow.md)|Fait défiler la zone cliente spécifiée.|  
|[CWindow::ScrollWindowEx](../Topic/CWindow::ScrollWindowEx.md)|Fait défiler la zone cliente spécifiée avec des fonctionnalités supplémentaires.|  
|[CWindow::SendDlgItemMessage](../Topic/CWindow::SendDlgItemMessage.md)|Envoie un message à un contrôle.|  
|[CWindow::SendMessage](../Topic/CWindow::SendMessage.md)|Envoie un message dans la fenêtre et ne retourne pas tant que la procédure de fenêtre a traité le message.|  
|[CWindow::SendMessageToDescendants](../Topic/CWindow::SendMessageToDescendants.md)|Envoie un message dans les fenêtres enfants spécifiées.|  
|[CWindow::SendNotifyMessage](../Topic/CWindow::SendNotifyMessage.md)|Envoie un message dans la fenêtre.  Si la fenêtre est créée par le thread appelant, `SendNotifyMessage` ne retourne pas tant que la procédure de fenêtre a traité le message.  Sinon, elle retourne immédiatement.|  
|[CWindow::SetActiveWindow](../Topic/CWindow::SetActiveWindow.md)|Active la fenêtre.|  
|[CWindow::SetCapture](../Topic/CWindow::SetCapture.md)|Envoie toutes les entrées de la souris ultérieure à la fenêtre.|  
|[CWindow::SetClipboardViewer](../Topic/CWindow::SetClipboardViewer.md)|Ajoute la fenêtre à la chaîne de presse\-papiers.|  
|[CWindow::SetDlgCtrlID](../Topic/CWindow::SetDlgCtrlID.md)|Modifie l'identificateur de la fenêtre.|  
|[CWindow::SetDlgItemInt](../Topic/CWindow::SetDlgItemInt.md)|Modifie le texte d'un contrôle en représentation sous forme de chaîne d'une valeur entière.|  
|[CWindow::SetDlgItemText](../Topic/CWindow::SetDlgItemText.md)|Modifie le texte d'un contrôle.|  
|[CWindow::SetFocus](../Topic/CWindow::SetFocus.md)|Place le focus d'entrée dans la fenêtre.|  
|[CWindow::SetFont](../Topic/CWindow::SetFont.md)|Modifie la police actuelle de la fenêtre.|  
|[CWindow::SetHotKey](../Topic/CWindow::SetHotKey.md)|Associe une touche d'accès rapide à la fenêtre.|  
|[CWindow::SetIcon](../Topic/CWindow::SetIcon.md)|Modifie la fenêtre grande ou la petite icône.|  
|[CWindow::SetMenu](../Topic/CWindow::SetMenu.md)|Modifie le menu actuel de la fenêtre.|  
|[CWindow::SetParent](../Topic/CWindow::SetParent.md)|Modifie la fenêtre parente.|  
|[CWindow::SetRedraw](../Topic/CWindow::SetRedraw.md)|Définit ou espaces libres l'indicateur redessiner.|  
|[CWindow::SetScrollInfo](../Topic/CWindow::SetScrollInfo.md)|Définit les paramètres d'une barre de défilement.|  
|[CWindow::SetScrollPos](../Topic/CWindow::SetScrollPos.md)|Modifie la position de la case de défilement.|  
|[CWindow::SetScrollRange](../Topic/CWindow::SetScrollRange.md)|Modifie l'intervalle de barre de défilement.|  
|[CWindow::SetTimer](../Topic/CWindow::SetTimer.md)|Crée un événement de minuterie.|  
|[CWindow::SetWindowContextHelpId](../Topic/CWindow::SetWindowContextHelpId.md)|Définit l'identificateur de contexte d'aide de la fenêtre.|  
|[CWindow::SetWindowLong](../Topic/CWindow::SetWindowLong.md)|Définit une valeur 32 bits à un offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::SetWindowLongPtr](../Topic/CWindow::SetWindowLongPtr.md)|Modifie un attribut de la fenêtre spécifiée, et définit également une valeur à l'offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::SetWindowPlacement](../Topic/CWindow::SetWindowPlacement.md)|Définit l'état et les positions show.|  
|[CWindow::SetWindowPos](../Topic/CWindow::SetWindowPos.md)|Définit la taille, la position, et l'ordre de plan.|  
|[CWindow::SetWindowRgn](../Topic/CWindow::SetWindowRgn.md)|Définit la zone de la fenêtre d'une fenêtre.|  
|[CWindow::SetWindowText](../Topic/CWindow::SetWindowText.md)|Modifie le texte de la fenêtre.|  
|[CWindow::SetWindowWord](../Topic/CWindow::SetWindowWord.md)|Définit une valeur 16 bits à un offset spécifié dans la mémoire supplémentaire de fenêtre.|  
|[CWindow::ShowCaret](../Topic/CWindow::ShowCaret.md)|Affiche le signe insertion.|  
|[CWindow::ShowOwnedPopups](../Topic/CWindow::ShowOwnedPopups.md)|Affiche ou masque les fenêtres indépendantes détenues par la fenêtre.|  
|[CWindow::ShowScrollBar](../Topic/CWindow::ShowScrollBar.md)|Affiche ou masque un barre de défilement.|  
|[CWindow::ShowWindow](../Topic/CWindow::ShowWindow.md)|Définit l'état du afficher de la fenêtre.|  
|[CWindow::ShowWindowAsync](../Topic/CWindow::ShowWindowAsync.md)|Définit l'état show d'une fenêtre créée par un thread différent.|  
|[CWindow::UpdateWindow](../Topic/CWindow::UpdateWindow.md)|Met à jour la zone cliente.|  
|[CWindow::ValidateRect](../Topic/CWindow::ValidateRect.md)|Valide la zone cliente dans le rectangle spécifié.|  
|[CWindow::ValidateRgn](../Topic/CWindow::ValidateRgn.md)|Valide la zone cliente dans la zone spécifiée.|  
|[CWindow::WinHelp](../Topic/CWindow::WinHelp.md)|Démarre l'aide de windows.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindow::operator HWND](../Topic/CWindow::operator%20HWND.md)|Convertit l'objet d' `CWindow` à `HWND`.|  
|[CWindow::operator \=](../Topic/CWindow::operator%20=.md)|Assigne `HWND` à l'objet d' `CWindow` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindow::m\_hWnd](../Topic/CWindow::m_hWnd.md)|Le handle dans la fenêtre associé à l'objet d' `CWindow` .|  
|[CWindow::rcDefault](../Topic/CWindow::rcDefault.md)|Contient les dimensions de fenêtre par défaut.|  
  
## Notes  
 `CWindow` fournit les fonctionnalités de base pour manipuler une fenêtre dans ATL.  De nombreuses enveloppe l'une des méthodes d' `CWindow` simplement de l'API Win32 s'exécute.  Par exemple, comparez les prototypes pour `CWindow::ShowWindow` et `ShowWindow`:  
  
|Méthode de CWindow|Fonction Win32|  
|------------------------|--------------------|  
|**BOOL ShowWindow\( int**  `nCmdShow`\);|**BOOL ShowWindow\( HWND**  `hWnd` **, int**  `nCmdShow`\);|  
  
 `CWindow::ShowWindow` appelle la fonction `ShowWindow` Win32 en passant `CWindow::m_hWnd` comme premier paramètre.  Chaque méthode d' `CWindow` qui encapsule directement une fonction Win32 passe le membre d' `m_hWnd` ; par conséquent, une grande partie de la documentation d' `CWindow` vous retourne à [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Chaque fonction non liée à la fenêtre Win32 est encapsulé par `CWindow`, et qui encapsule non chaque méthode d' `CWindow` une fonction Win32.  
  
 `CWindow::m_hWnd` stocke `HWND` qui identifie une fenêtre.  `HWND` est attaché à votre objet lorsque vous :  
  
-   Spécifiez `HWND` dans le constructeur d'`CWindow`.  
  
-   Appelez `CWindow::Attach`.  
  
-   **operator \=**d'`CWindow` d'utilisation.  
  
-   Le créez ou sous\-classe qu'une fenêtre à l'aide d'une des classes suivantes est dérivée d' `CWindow`:  
  
     [CWindowImpl](../../atl/reference/cwindowimpl-class.md) vous permet de créer une fenêtre ou une sous\-classe une fenêtre existante.  
  
     [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) implémente une fenêtre contenue dans un autre objet.  Vous pouvez créer une fenêtre ou une sous\-classe une fenêtre existante.  
  
     [CDialogImpl](../../atl/reference/cdialogimpl-class.md) vous permet de créer un modal ou une boîte de dialogue non modale.  
  
 Pour plus d'informations sur les fenêtres, consultez [fenêtres](http://msdn.microsoft.com/library/windows/desktop/ms632595) et les rubriques suivants dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Pour plus d'informations sur l'utilisation des fenêtres dans ATL, consultez l'article [Classes de fenêtres ATL](../../atl/atl-window-classes.md).  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)