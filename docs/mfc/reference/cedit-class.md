---
title: "CEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEdit class"
  - "controls [MFC], edit"
  - "edit controls"
  - "edit controls, classes"
  - "line separators in multiline edit controls"
  - "multiline edit control"
  - "séparateurs, in multiline edit controls"
  - "text editors"
  - "text editors, CEdit class"
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'un contrôle d'édition windows.  
  
## Syntaxe  
  
```  
class CEdit : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CEdit::CEdit](../Topic/CEdit::CEdit.md)|Crée un objet de contrôle d' `CEdit` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CEdit::CanUndo](../Topic/CEdit::CanUndo.md)|Détermine si une opération de service peut être annulée.|  
|[CEdit::CharFromPos](../Topic/CEdit::CharFromPos.md)|Extrait la ligne et les index de caractère pour le caractère le plus proche d'une position spécifiée.|  
|[CEdit::Clear](../Topic/CEdit::Clear.md)|Supprime \(espaces inscription\) la sélection actuelle \(le cas échéant\) dans le contrôle d'édition.|  
|[CEdit::Copy](../Topic/CEdit::Copy.md)|Copie la sélection actuelle \(le cas échéant\) dans le contrôle d'édition au presse\-papiers dans le format de **CF\_TEXT** .|  
|[CEdit::Create](../Topic/CEdit::Create.md)|Crée le contrôle d'édition windows et l'attache à l'objet d' `CEdit` .|  
|[CEdit::Cut](../Topic/CEdit::Cut.md)|Supprime coupes \(\) la sélection actuelle \(le cas échéant\) dans le contrôle d'édition et les copie le texte supprimé au presse\-papiers dans le format de **CF\_TEXT** .|  
|[CEdit::EmptyUndoBuffer](../Topic/CEdit::EmptyUndoBuffer.md)|Réinitialise \(espaces inscription\) la balise d'annulation d'un contrôle d'édition.|  
|[CEdit::FmtLines](../Topic/CEdit::FmtLines.md)|Définit l'inclusion des caractères de soulignement mous désactiver dans un contrôle d'édition multiligne.|  
|[CEdit::GetCueBanner](../Topic/CEdit::GetCueBanner.md)|Extrait le texte affiché comme un caractère indicateur de texte, ou la fin, dans un contrôle d'édition lorsque le contrôle est vide et n'a pas le focus.|  
|[CEdit::GetFirstVisibleLine](../Topic/CEdit::GetFirstVisibleLine.md)|Détermine la ligne visible le plus élevé un contrôle d'édition.|  
|[CEdit::GetHandle](../Topic/CEdit::GetHandle.md)|Récupère un handle vers la mémoire qui est actuellement allouée pour un contrôle d'édition multiligne.|  
|[CEdit::GetHighlight](../Topic/CEdit::GetHighlight.md)|Obtient les index des caractères de début et de fin d'une plage de texte mis en surbrillance dans le contrôle d'édition actuel.|  
|[CEdit::GetLimitText](../Topic/CEdit::GetLimitText.md)|Obtient la quantité maximale de texte que cet `CEdit` peut contenir.|  
|[CEdit::GetLine](../Topic/CEdit::GetLine.md)|Extrait une ligne de texte d'un contrôle d'édition.|  
|[CEdit::GetLineCount](../Topic/CEdit::GetLineCount.md)|Récupère le nombre de lignes dans un contrôle d'édition multiligne.|  
|[CEdit::GetMargins](../Topic/CEdit::GetMargins.md)|Obtient les marges gauche et droite pour cet `CEdit`.|  
|[CEdit::GetModify](../Topic/CEdit::GetModify.md)|Détermine si le contenu d'un contrôle d'édition a été modifié.|  
|[CEdit::GetPasswordChar](../Topic/CEdit::GetPasswordChar.md)|Récupère le caractère de mot de passe affiché dans un contrôle d'édition lorsque l'utilisateur entre dans le texte.|  
|[CEdit::GetRect](../Topic/CEdit::GetRect.md)|Obtient le rectangle de mise en forme d'un contrôle d'édition.|  
|[CEdit::GetSel](../Topic/CEdit::GetSel.md)|Obtient la première et la dernière positions d'impression de la sélection actuelle dans un contrôle d'édition.|  
|[CEdit::HideBalloonTip](../Topic/CEdit::HideBalloonTip.md)|Masque une info\-bulle associée au contrôle d'édition actuel.|  
|[CEdit::LimitText](../Topic/CEdit::LimitText.md)|Limite la longueur du texte que l'utilisateur peut entrer dans un contrôle d'édition.|  
|[CEdit::LineFromChar](../Topic/CEdit::LineFromChar.md)|Récupère le numéro de ligne de la ligne qui contient l'index du caractère spécifié.|  
|[CEdit::LineIndex](../Topic/CEdit::LineIndex.md)|Récupère l'index du caractère d'une ligne dans un contrôle d'édition multiligne.|  
|[CEdit::LineLength](../Topic/CEdit::LineLength.md)|Extrait la longueur d'une ligne dans un contrôle d'édition.|  
|[CEdit::LineScroll](../Topic/CEdit::LineScroll.md)|Fait défiler le texte d'un contrôle d'édition multiligne.|  
|[CEdit::Paste](../Topic/CEdit::Paste.md)|Insère les données du presse\-papiers dans le contrôle d'édition à la position du curseur actuelle.  Les données sont insérées que si le presse\-papiers contient des données au format de **CF\_TEXT** .|  
|[CEdit::PosFromChar](../Topic/CEdit::PosFromChar.md)|Récupère les coordonnées de l'angle supérieur gauche d'un index du caractère spécifié.|  
|[CEdit::ReplaceSel](../Topic/CEdit::ReplaceSel.md)|Remplace la sélection actuelle dans un contrôle d'édition par le texte spécifié.|  
|[CEdit::SetCueBanner](../Topic/CEdit::SetCueBanner.md)|Définit le texte affiché comme un caractère indicateur de texte, ou la fin, dans un contrôle d'édition lorsque le contrôle est vide et n'a pas le focus.|  
|[CEdit::SetHandle](../Topic/CEdit::SetHandle.md)|Définit le handle vers la mémoire locale qui sera utilisée par un contrôle d'édition multiligne.|  
|[CEdit::SetHighlight](../Topic/CEdit::SetHighlight.md)|Met en surbrillance une plage de texte affiché dans le contrôle d'édition actuel.|  
|[CEdit::SetLimitText](../Topic/CEdit::SetLimitText.md)|Définit la quantité maximale de texte que cet `CEdit` peut contenir.|  
|[CEdit::SetMargins](../Topic/CEdit::SetMargins.md)|Définit les marges gauche et droite pour cet `CEdit`.|  
|[CEdit::SetModify](../Topic/CEdit::SetModify.md)|Définit ou espaces libres la balise de modification pour un contrôle d'édition.|  
|[CEdit::SetPasswordChar](../Topic/CEdit::SetPasswordChar.md)|Définit ou supprime un caractère de mot de passe affiché dans un contrôle d'édition lorsque l'utilisateur entre dans le texte.|  
|[CEdit::SetReadOnly](../Topic/CEdit::SetReadOnly.md)|Définit l'état de lecture seule d'un contrôle d'édition.|  
|[CEdit::SetRect](../Topic/CEdit::SetRect.md)|Définit le rectangle de mise en forme d'un contrôle d'édition multiligne et met à jour le contrôle.|  
|[CEdit::SetRectNP](../Topic/CEdit::SetRectNP.md)|Définit le rectangle de mise en forme d'un contrôle d'édition multiligne sans repeindre la fenêtre du contrôle.|  
|[CEdit::SetSel](../Topic/CEdit::SetSel.md)|Sélectionne une plage de caractères dans un contrôle d'édition.|  
|[CEdit::SetTabStops](../Topic/CEdit::SetTabStops.md)|Définit les taquets de tabulation dans un contrôle d'édition multiligne.|  
|[CEdit::ShowBalloonTip](../Topic/CEdit::ShowBalloonTip.md)|Affiche une info\-bulle associée au contrôle d'édition actuel.|  
|[CEdit::Undo](../Topic/CEdit::Undo.md)|Inverse la dernière opération de service.|  
  
## Notes  
 Un contrôle d'édition est une fenêtre enfant rectangulaire dans laquelle l'utilisateur peut entrer du texte.  
  
 Vous pouvez créer un contrôle d'édition d'un modèle de boîte de dialogue ou directement dans votre code.  Dans les deux cas, abord appeler le constructeur `CEdit` pour construire l'objet d' `CEdit` , puis d'appeler la fonction membre de [Create](../Topic/CEdit::Create.md) pour créer le contrôle d'édition windows et pour la liaison à l'objet d' `CEdit` .  
  
 La construction peut être un processus à une étape dans une classe dérivée d' `CEdit`.  Entrez un constructeur pour la classe dérivée et appelez **Créer** du constructeur.  
  
 `CEdit` hérite de la fonctionnalité importante d' `CWnd`.  Pour définir et récupérer le texte d'un objet d' `CEdit` , utilisez les fonctions membres [SetWindowText](../Topic/CWnd::SetWindowText.md) et [GetWindowText](../Topic/CWnd::GetWindowText.md)d' `CWnd` , qui définissent ou obtiennent tout le contenu d'un contrôle d'édition, même s'il s'agit d'un contrôle multiligne.  Des lignes de texte dans un contrôle multiligne sont séparées par des séquences de caractères « \\ r \\ n ».  Également, si un contrôle d'édition est multiligne, obtenir et définir une partie du texte du contrôle en appelant les fonctions membres d' `CEdit`[GetLine](../Topic/CEdit::GetLine.md), [SetSel](../Topic/CEdit::SetSel.md), [GetSel](../Topic/CEdit::GetSel.md), et [ReplaceSel](../Topic/CEdit::ReplaceSel.md).  
  
 Si vous souhaitez gérer des messages de notification de fenêtres envoyés par un contrôle d'édition à son parent \(généralement une classe dérivée d' `CDialog`\), ajoutez une entrée de la table des messages et une fonction membre gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de la table des messages prend la forme suivante :  
  
 identificateur de**\(**de notification d'**ON\_***, memberFxn***\)**  
  
 où `id` spécifie l'ID de fenêtre enfant du contrôle d'édition envoyant la notification, et `memberFxn` est le nom de la fonction membre parente que vous avez écrit pour traiter la notification.  
  
 Le prototype de fonction du parent est la suivante :  
  
 memberFxn**\( \);**de void d'**afx\_msg**  
  
 Voici une liste d'entrées de la table des messages potentiels et une description des cas où elle est envoyée au parent :  
  
-   **ON\_EN\_CHANGE** l'utilisateur a pris une action qui peut avoir modifié le texte dans un contrôle d'édition.  Contrairement au message de notification d' **EN\_UPDATE** , ce message de notification est envoyé après les mises à jour de l'affichage.  
  
-   **ON\_EN\_ERRSPACE** le contrôle d'édition ne peut pas allouer suffisamment de mémoire pour accepter une demande spécifique.  
  
-   **ON\_EN\_HSCROLL** l'utilisateur clique sur la barre de défilement horizontale d'un contrôle d'édition.  Est averti la fenêtre parente avant que l'écran mis à jour.  
  
-   **ON\_EN\_KILLFOCUS** le contrôle d'édition perd le focus d'entrée.  
  
-   **ON\_EN\_MAXTEXT** l'implémentation actuelle a dépassé le nombre spécifié de caractères pour le contrôle d'édition et a été tronqué.  Également envoyé lorsqu'un contrôle d'édition n'a pas le style d' **ES\_AUTOHSCROLL** et le nombre de caractères à insérer dépasserait la largeur du contrôle d'édition.  Également envoyé lorsqu'un contrôle d'édition n'a pas le style d' **ES\_AUTOVSCROLL** et le nombre total de lignes résulter d'une insertion de texte dépasserait la hauteur du contrôle d'édition.  
  
-   **ON\_EN\_SETFOCUS** l'a envoyé lorsqu'un contrôle d'édition reçoit le focus d'entrée.  
  
-   **ON\_EN\_UPDATE** le contrôle d'édition est autour de le texte modifié par affichage.  Envoyé fois que le contrôle a mis en forme du texte mais avant qu'il examine le texte afin que la taille de la fenêtre puisse être modifiée, si nécessaire.  
  
-   **ON\_EN\_VSCROLL** l'utilisateur clique sur la barre de défilement verticale d'un contrôle d'édition.  Est averti la fenêtre parente avant que l'écran mis à jour.  
  
 Si vous créez un objet d' `CEdit` dans une boîte de dialogue, l'objet d' `CEdit` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CEdit` d'une ressource de boîte de dialogue à l'aide de l'éditeur de boîtes de dialogue, l'objet d' `CEdit` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CEdit` dans une fenêtre, vous devrez peut\-être également la destruction.  Si vous créez l'objet d' `CEdit` sur la pile, elle est perdue automatiquement.  Si vous créez l'objet d' `CEdit` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque l'utilisateur exécute le contrôle d'édition windows.  Si vous allouez une mémoire de l'objet d' `CEdit` , remplacez le destructeur d' `CEdit` pour disposer les allocations.  
  
 Pour modifier certains styles dans un contrôle d'édition \(tel qu' **ES\_READONLY**\) vous devez envoyer des messages spécifiques au contrôle au lieu d'utiliser [ModifyStyle](../Topic/CWnd::ModifyStyle.md).  Consultez [styles de contrôle d'édition](http://msdn.microsoft.com/library/windows/desktop/bb775464) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur `CEdit`, consultez :  
  
-   [Contrôles](../../mfc/controls-mfc.md)  
  
-   Article de la Base de connaissances Q259949 : LES INFO : SetCaretPos\(\) n'est pas approprié avec CEdit ou contrôles de CRichEditCtrl  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CEdit`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [exemple MFC CALCDRIV](../../top/visual-cpp-samples.md)   
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)