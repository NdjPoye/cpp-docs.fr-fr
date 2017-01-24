---
title: "CToolBarCtrl Class | Microsoft Docs"
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
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl class"
  - "info-bulles (C++), notifications"
  - "contrôles de barre d'outils (MFC), CToolBarCtrl class"
  - "Windows common controls [C++], CToolBarCtrl"
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle commun de barre d'outils windows.  
  
## Syntaxe  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolBarCtrl::CToolBarCtrl](../Topic/CToolBarCtrl::CToolBarCtrl.md)|Construit un objet `CToolBarCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolBarCtrl::AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)|Ajoute un ou plusieurs images de bouton bitmap à la liste d'images de bouton disponibles pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::AddButtons](../Topic/CToolBarCtrl::AddButtons.md)|Ajoute un ou plusieurs boutons à un contrôle de barre d'outils.|  
|[CToolBarCtrl::AddString](../Topic/CToolBarCtrl::AddString.md)|Ajoute une nouvelle chaîne, passée comme un ID de ressource, à la liste interne de la barre d'outils de chaînes.|  
|[CToolBarCtrl::AddStrings](../Topic/CToolBarCtrl::AddStrings.md)|Ajoute une nouvelle chaîne ou chaînes, passées comme un pointeur vers une mémoire tampon des chaînes null séparées, à la liste interne de la barre d'outils de chaînes.|  
|[CToolBarCtrl::AutoSize](../Topic/CToolBarCtrl::AutoSize.md)|Redimensionne un contrôle de barre d'outils.|  
|[CToolBarCtrl::ChangeBitmap](../Topic/CToolBarCtrl::ChangeBitmap.md)|Modifie la bitmap d'un bouton dans le contrôle de barre d'outils en cours.|  
|[CToolBarCtrl::CheckButton](../Topic/CToolBarCtrl::CheckButton.md)|Contrôles ou espaces libres un bouton donné dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::CommandToIndex](../Topic/CToolBarCtrl::CommandToIndex.md)|Extrait l'index de base zéro pour le bouton associé à l'identificateur de commande spécifié.|  
|[CToolBarCtrl::Create](../Topic/CToolBarCtrl::Create.md)|Crée un contrôle de barre d'outils et l'attache à un objet d' `CToolBarCtrl` .|  
|[CToolBarCtrl::CreateEx](../Topic/CToolBarCtrl::CreateEx.md)|Crée un contrôle de barre d'outils avec les styles étendus par windows spécifiées et l'attache à un objet d' `CToolBarCtrl` .|  
|[CToolBarCtrl::Customize](../Topic/CToolBarCtrl::Customize.md)|Affiche la boîte de dialogue de barre d'outils de personnaliser.|  
|[CToolBarCtrl::DeleteButton](../Topic/CToolBarCtrl::DeleteButton.md)|Supprime un bouton du contrôle de barre d'outils.|  
|[CToolBarCtrl::EnableButton](../Topic/CToolBarCtrl::EnableButton.md)|Active ou désactive le bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetAnchorHighlight](../Topic/CToolBarCtrl::GetAnchorHighlight.md)|Extrait la configuration de surbrillance d'ancrage d'une barre d'outils.|  
|[CToolBarCtrl::GetBitmap](../Topic/CToolBarCtrl::GetBitmap.md)|Extrait l'index de la bitmap associée à un bouton dans une barre d'outils.|  
|[CToolBarCtrl::GetBitmapFlags](../Topic/CToolBarCtrl::GetBitmapFlags.md)|Obtient les balises associées à la bitmap de la barre d'outils.|  
|[CToolBarCtrl::GetButton](../Topic/CToolBarCtrl::GetButton.md)|Récupère des informations sur le bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetButtonCount](../Topic/CToolBarCtrl::GetButtonCount.md)|Récupère un nombre des boutons actuel dans le contrôle de barre d'outils.|  
|[CToolBarCtrl::GetButtonInfo](../Topic/CToolBarCtrl::GetButtonInfo.md)|Récupère les informations d'un bouton dans une barre d'outils.|  
|[CToolBarCtrl::GetButtonSize](../Topic/CToolBarCtrl::GetButtonSize.md)|Extrait la largeur et la hauteur actuelle des boutons de barre d'outils, en pixels.|  
|[CToolBarCtrl::GetColorScheme](../Topic/CToolBarCtrl::GetColorScheme.md)|Récupère le modèle de couleurs du contrôle de barre d'outils en cours.|  
|[CToolBarCtrl::GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md)|Récupère la liste d'images qu'un contrôle de barre d'outils utilise pour afficher les boutons désactivés.|  
|[CToolBarCtrl::GetDropTarget](../Topic/CToolBarCtrl::GetDropTarget.md)|Récupère l'interface d' [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetExtendedStyle](../Topic/CToolBarCtrl::GetExtendedStyle.md)|Récupère les styles étendus pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)|Récupère la liste d'images qu'un contrôle de barre d'outils utilise pour afficher les boutons « chauds ».  Un bouton en cours apparaît en surbrillance lorsque le pointeur de la souris est au\-dessus.|  
|[CToolBarCtrl::GetHotItem](../Topic/CToolBarCtrl::GetHotItem.md)|Extrait l'index de l'élément réactif dans une barre d'outils.|  
|[CToolBarCtrl::GetImageList](../Topic/CToolBarCtrl::GetImageList.md)|Récupère la liste d'images qu'un contrôle de barre d'outils utilise pour afficher des boutons dans leur état par défaut.|  
|[CToolBarCtrl::GetInsertMark](../Topic/CToolBarCtrl::GetInsertMark.md)|Extrait la marque d'insertion actuel de la barre d'outils.|  
|[CToolBarCtrl::GetInsertMarkColor](../Topic/CToolBarCtrl::GetInsertMarkColor.md)|Extrait la couleur utilisée pour dessiner la marque d'insertion de la barre d'outils.|  
|[CToolBarCtrl::GetItemRect](../Topic/CToolBarCtrl::GetItemRect.md)|Récupère le rectangle englobant d'un bouton dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetMaxSize](../Topic/CToolBarCtrl::GetMaxSize.md)|Extrait la taille totale de tous les boutons et séparateurs visibles dans la barre d'outils.|  
|[CToolBarCtrl::GetMaxTextRows](../Topic/CToolBarCtrl::GetMaxTextRows.md)|Récupère le nombre de lignes de texte affichent sur un bouton de barre d'outils.|  
|[CToolBarCtrl::GetMetrics](../Topic/CToolBarCtrl::GetMetrics.md)|Extrait la métrique d'un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetPadding](../Topic/CToolBarCtrl::GetPadding.md)|Extrait la marge intérieure horizontale et verticale du contrôle de barre d'outils en cours.|  
|[CToolBarCtrl::GetPressedImageList](../Topic/CToolBarCtrl::GetPressedImageList.md)|Récupère la liste d'images que le contrôle de barre d'outils actuellement l'utilise pour représenter des boutons dans l'état enfoncé.|  
|[CToolBarCtrl::GetRect](../Topic/CToolBarCtrl::GetRect.md)|Récupère le rectangle englobant d'un bouton de barre d'outils spécifié.|  
|[CToolBarCtrl::GetRows](../Topic/CToolBarCtrl::GetRows.md)|Récupère le nombre de lignes de boutons actuellement affichés dans la barre d'outils.|  
|[CToolBarCtrl::GetState](../Topic/CToolBarCtrl::GetState.md)|Récupère des informations sur l'état du bouton spécifié dans un contrôle de barre d'outils, par exemple s'il est activé, enfoncé, ou contrôlé.|  
|[CToolBarCtrl::GetString](../Topic/CToolBarCtrl::GetString.md)|Extrait une chaîne de barre d'outils.|  
|[CToolBarCtrl::GetStyle](../Topic/CToolBarCtrl::GetStyle.md)|Récupère les styles en cours de utilisation pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md)|Récupère le handle du contrôle d'info\-bulle, le cas échéant, associé au contrôle de barre d'outils.|  
|[CToolBarCtrl::HideButton](../Topic/CToolBarCtrl::HideButton.md)|Masque ou affiche le bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::HitTest](../Topic/CToolBarCtrl::HitTest.md)|Détermine si un point se situe dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::Indeterminate](../Topic/CToolBarCtrl::Indeterminate.md)|Définit ou espaces libres l'état \(gris\) indéterminé du bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::InsertButton](../Topic/CToolBarCtrl::InsertButton.md)|Insère un bouton dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::InsertMarkHitTest](../Topic/CToolBarCtrl::InsertMarkHitTest.md)|Extrait les informations de marque d'insertion pour un point dans une barre d'outils.|  
|[CToolBarCtrl::IsButtonChecked](../Topic/CToolBarCtrl::IsButtonChecked.md)|Indique si le bouton spécifié dans un contrôle de barre d'outils est activée.|  
|[CToolBarCtrl::IsButtonEnabled](../Topic/CToolBarCtrl::IsButtonEnabled.md)|Indique si le bouton spécifié dans un contrôle de barre d'outils est activé.|  
|[CToolBarCtrl::IsButtonHidden](../Topic/CToolBarCtrl::IsButtonHidden.md)|Indique si le bouton spécifié dans un contrôle de barre d'outils est masquée.|  
|[CToolBarCtrl::IsButtonHighlighted](../Topic/CToolBarCtrl::IsButtonHighlighted.md)|Contrôle l'état de mise en surbrillance du bouton de barre d'outils.|  
|[CToolBarCtrl::IsButtonIndeterminate](../Topic/CToolBarCtrl::IsButtonIndeterminate.md)|Indique si l'état du bouton spécifié dans un contrôle de barre d'outils est indéterminé \(gris\).|  
|[CToolBarCtrl::IsButtonPressed](../Topic/CToolBarCtrl::IsButtonPressed.md)|Indique si le bouton spécifié dans un contrôle de barre d'outils est enfoncé.|  
|[CToolBarCtrl::LoadImages](../Topic/CToolBarCtrl::LoadImages.md)|Bitmap de charge dans la liste d'images d'un contrôle de barre d'outils.|  
|[CToolBarCtrl::MapAccelerator](../Topic/CToolBarCtrl::MapAccelerator.md)|Mappe un caractère d'accélérateur à un bouton de barre d'outils.|  
|[CToolBarCtrl::MarkButton](../Topic/CToolBarCtrl::MarkButton.md)|Définit l'état de mise en surbrillance d'un bouton donné dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::MoveButton](../Topic/CToolBarCtrl::MoveButton.md)|Déplace un bouton d'un index à un autre.|  
|[CToolBarCtrl::PressButton](../Topic/CToolBarCtrl::PressButton.md)|Pressions ou release le bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::ReplaceBitmap](../Topic/CToolBarCtrl::ReplaceBitmap.md)|Remplace la bitmap existante dans le contrôle de barre d'outils en cours par une nouvelle bitmap.|  
|[CToolBarCtrl::RestoreState](../Topic/CToolBarCtrl::RestoreState.md)|Restaure l'état du contrôle de barre d'outils.|  
|[CToolBarCtrl::SaveState](../Topic/CToolBarCtrl::SaveState.md)|Enregistre l'état du contrôle de barre d'outils.|  
|[CToolBarCtrl::SetAnchorHighlight](../Topic/CToolBarCtrl::SetAnchorHighlight.md)|Définit la configuration de surbrillance d'ancrage d'une barre d'outils.|  
|[CToolBarCtrl::SetBitmapSize](../Topic/CToolBarCtrl::SetBitmapSize.md)|Définit la taille des images générées une correspondance de bits à ajouter à un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)|Définit les informations d'un bouton existant dans une barre d'outils.|  
|[CToolBarCtrl::SetButtonSize](../Topic/CToolBarCtrl::SetButtonSize.md)|Définit la taille des boutons à ajouter à un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetButtonStructSize](../Topic/CToolBarCtrl::SetButtonStructSize.md)|Spécifie la taille de la structure d' `TBBUTTON` .|  
|[CToolBarCtrl::SetButtonWidth](../Topic/CToolBarCtrl::SetButtonWidth.md)|Définit le minimum et la largeur maximale de bouton dans le contrôle de barre d'outils.|  
|[CToolBarCtrl::SetCmdID](../Topic/CToolBarCtrl::SetCmdID.md)|Définit l'identificateur de commande à envoyer à la fenêtre propriétaire lorsque le bouton spécifié est enfoncé.|  
|[CToolBarCtrl::SetColorScheme](../Topic/CToolBarCtrl::SetColorScheme.md)|Définit le modèle de couleurs du contrôle de barre d'outils en cours.|  
|[CToolBarCtrl::SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)|Définit la liste d'images que le contrôle de barre d'outils utilisera pour afficher les boutons désactivés.|  
|[CToolBarCtrl::SetDrawTextFlags](../Topic/CToolBarCtrl::SetDrawTextFlags.md)|Définit les balises dans la fonction [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), qui Win32 est utilisée pour dessiner le texte dans le rectangle spécifié, mis en forme en fonction de la façon dont les balises sont définies.|  
|[CToolBarCtrl::SetExtendedStyle](../Topic/CToolBarCtrl::SetExtendedStyle.md)|Définit les styles étendus pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)|Définit la liste d'images que le contrôle de barre d'outils utilisera pour afficher les boutons « chauds ».|  
|[CToolBarCtrl::SetHotItem](../Topic/CToolBarCtrl::SetHotItem.md)|Définit l'élément réactif dans une barre d'outils.|  
|[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)|Définit la liste d'images que la barre d'outils utilisera pour afficher des boutons qui sont dans leur état par défaut.|  
|[CToolBarCtrl::SetIndent](../Topic/CToolBarCtrl::SetIndent.md)|Définit la mise en retrait pour le premier bouton dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetInsertMark](../Topic/CToolBarCtrl::SetInsertMark.md)|Définit la marque d'insertion actuel de la barre d'outils.|  
|[CToolBarCtrl::SetInsertMarkColor](../Topic/CToolBarCtrl::SetInsertMarkColor.md)|Définit la couleur utilisée pour dessiner la marque d'insertion de la barre d'outils.|  
|[CToolBarCtrl::SetMaxTextRows](../Topic/CToolBarCtrl::SetMaxTextRows.md)|Définit le nombre de lignes de texte affichent sur un bouton de barre d'outils.|  
|[CToolBarCtrl::SetMetrics](../Topic/CToolBarCtrl::SetMetrics.md)|Définit la métrique d'un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetOwner](../Topic/CToolBarCtrl::SetOwner.md)|Définit la fenêtre pour recevoir des messages de notification du contrôle de barre d'outils.|  
|[CToolBarCtrl::SetPadding](../Topic/CToolBarCtrl::SetPadding.md)|Définit la marge intérieure horizontale et verticale du contrôle de barre d'outils en cours.|  
|[CToolBarCtrl::SetPressedImageList](../Topic/CToolBarCtrl::SetPressedImageList.md)|Définit la liste d'images que le contrôle de barre d'outils actuellement l'utilise pour représenter des boutons dans l'état enfoncé.|  
|[CToolBarCtrl::SetRows](../Topic/CToolBarCtrl::SetRows.md)|Définit le nombre de lignes de boutons affichent dans la barre d'outils.|  
|[CToolBarCtrl::SetState](../Topic/CToolBarCtrl::SetState.md)|Définit l'état du bouton spécifié dans un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetStyle](../Topic/CToolBarCtrl::SetStyle.md)|Définit les styles pour un contrôle de barre d'outils.|  
|[CToolBarCtrl::SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)|Associe un contrôle d'info\-bulle avec le contrôle de barre d'outils.|  
|[CToolBarCtrl::SetWindowTheme](../Topic/CToolBarCtrl::SetWindowTheme.md)|Définit le style visuel d'un contrôle de barre d'outils.|  
  
## Notes  
 Ce contrôle \(et par conséquent la classe d' `CToolBarCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Un contrôle commun de barre d'outils windows est une fenêtre enfant rectangulaire qui contient un ou plusieurs boutons.  Ces boutons peuvent afficher une image bitmap, une chaîne, ou les deux.  Lorsque l'utilisateur choisit un bouton, il envoie un message de commande dans la fenêtre propriétaire de la barre d'outils.  En général, les boutons d'une barre d'outils correspondent aux éléments du menu de l'application ; ils offrent un moyen plus directe pour que l'utilisateur accède aux commandes d'une application.  
  
 Les objets d'`CToolBarCtrl` contiennent plusieurs structures de données internes importantes : une liste de bitmap d'images de bouton ou d'une liste d'images, une liste d'étiquettes de bouton chaînes, et une liste de structures d' `TBBUTTON` qui associent une image chaîne et\/ou à la position, dénomment, l'état, et d'ID de commande du bouton.  Chacun des éléments de ces structures de données est indiqué par un index de base zéro.  Avant de pouvoir utiliser un objet d' `CToolBarCtrl` , vous devez installer ces structures de données.  La liste de chaînes ne peut être utilisée pour les étiquettes de bouton ; vous ne pouvez pas extraire des chaînes de la barre d'outils.  
  
 Pour utiliser un objet d' `CToolBarCtrl` , vous exécuterez généralement ces étapes :  
  
1.  Construisez l'objet d' `CToolBarCtrl` .  
  
2.  Appelez [Create](../Topic/CToolBarCtrl::Create.md) pour créer le contrôle commun de barre d'outils windows et le lier à l'objet d' `CToolBarCtrl` .  Pointez sur le style de la barre d'outils à l'aide de les styles, tels que **TBSTYLE\_TRANSPARENT** pour une barre d'outils transparente ou **TBSTYLE\_DROPDOWN** pour une barre d'outils qui prend en charge les boutons déroulants de style.  
  
3.  Identifiez la façon dont vous souhaitez les boutons de la barre d'outils affiche :  
  
    -   Pour utiliser des images bitmap pour les boutons, ajoutez des images de bouton à la barre d'outils en appelant [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md).  
  
    -   Pour utiliser des images restituées d'une liste d'images pour les boutons, spécifiez la liste d'images en appelant [SetImageList](../Topic/CToolBarCtrl::SetImageList.md), [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md), ou [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md).  
  
    -   Pour utiliser des étiquettes de chaîne pour des boutons, ajoutez les chaînes à la barre d'outils en appelant [AddString](../Topic/CToolBarCtrl::AddString.md) et\/ou [AddStrings](../Topic/CToolBarCtrl::AddStrings.md).  
  
4.  Ajoutez les squelettes de bouton à la barre d'outils en appelant [AddButtons](../Topic/CToolBarCtrl::AddButtons.md).  
  
5.  Si vous souhaitez que les info\-bulles pour un bouton de barre d'outils dans une fenêtre propriétaire qui n'est pas `CFrameWnd`, vous devez gérer les messages de **TTN\_NEEDTEXT** dans la fenêtre propriétaire de la barre d'outils comme décrit dans [notifications d'Info\-bulle de gestion](../../mfc/handling-tool-tip-notifications.md).  Si la fenêtre parente de la barre d'outils est dérivée d' `CFrameWnd`, les info\-bulles sont affichées sans effort supplémentaire de vous car `CFrameWnd` fournit un gestionnaire par défaut.  
  
6.  Si vous souhaitez que votre utilisateur pour pouvoir personnaliser la barre d'outils, gérer les messages de notification de personnalisation dans la fenêtre propriétaire comme décrit dans [notifications de personnalisation de gestion](../../mfc/handling-customization-notifications.md).  
  
 Vous pouvez utiliser [SaveState](../Topic/CToolBarCtrl::SaveState.md) pour enregistrer l'état actuel d'un contrôle de barre d'outils dans le Registre et [RestoreState](../Topic/CToolBarCtrl::RestoreState.md) pour restaurer l'état selon les informations précédemment stockées dans le Registre.  En plus de l'enregistrement de l'état de la barre d'outils entre les utilisations de l'application, mémoire des applications en général l'état avant que l'utilisateur commence personnalisation de la barre d'outils au cas où l'utilisateur souhaiterait ultérieurement restaurer la barre d'outils à son état d'origine.  
  
## Prise en charge la version 4,0 de microsoft Internet Explorer et versions ultérieures  
 Pour prendre en charge la fonctionnalité introduite dans Internet Explorer, la version 4,0 et ultérieure, MFC fournit la prise en charge de liste d'images et les styles transparents et en deux dimensions des contrôles de barre d'outils.  
  
 Une barre d'outils transparente permet au client situé sous la barre d'outils à afficher.  Pour créer une barre d'outils transparente, utilisez les styles de **TBSTYLE\_FLAT** et de **TBSTYLE\_TRANSPARENT** .  Les barres d'outils transparentes impliquent la sélection réactive ; autrement dit, lorsque le pointeur de la souris passe sur un bouton actif dans la barre d'outils, l'apparence du bouton change.  Les barres d'outils créées avec uniquement le style de **TBSTYLE\_FLAT** contiendront des boutons qui ne sont pas transparents.  
  
 La prise en charge de la liste d'images fournit une plus grande souplesse de contrôle du comportement par défaut, les images chaudes, et les images désactivées.  Utilisez [GetImageList](../Topic/CToolBarCtrl::GetImageList.md), [GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md), et [GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md) avec la barre d'outils transparente pour manipuler l'image en fonction de son état :  
  
 Pour plus d'informations sur l'utilisation `CToolBarCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolBarCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC exemple MFCIE](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)