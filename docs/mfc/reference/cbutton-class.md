---
title: "CButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "button control [MFC]"
  - "button objects (CButton)"
  - "CButton class"
  - "cases à cocher, button controls"
  - "checkbox buttons"
  - "pushbuttons"
  - "cases d'option, CButton class"
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités des contrôles bouton windows.  
  
## Syntaxe  
  
```  
class CButton : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CButton::CButton](../Topic/CButton::CButton.md)|Construit un objet `CButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CButton::Create](../Topic/CButton::Create.md)|Crée le contrôle bouton windows et l'attache à l'objet d' `CButton` .|  
|[CButton::DrawItem](../Topic/CButton::DrawItem.md)|Substitution pour dessiner un objet owner\-drawn d' `CButton` .|  
|[CButton::GetBitmap](../Topic/CButton::GetBitmap.md)|Récupère le handle de la bitmap précédemment définie avec [SetBitmap](../Topic/CButton::SetBitmap.md).|  
|[CButton::GetButtonStyle](../Topic/CButton::GetButtonStyle.md)|Récupère des informations sur le style de contrôle button.|  
|[CButton::GetCheck](../Topic/CButton::GetCheck.md)|Récupère l'état d'activation d'un contrôle bouton.|  
|[CButton::GetCursor](../Topic/CButton::GetCursor.md)|Récupère le handle de l'image de curseur précédemment définie avec [SetCursor](../Topic/CButton::SetCursor.md).|  
|[CButton::GetIcon](../Topic/CButton::GetIcon.md)|Récupère le handle de l'icône précédemment définie avec [SetIcon](../Topic/CButton::SetIcon.md).|  
|[CButton::GetIdealSize](../Topic/CButton::GetIdealSize.md)|Extrait la taille idéale du contrôle bouton.|  
|[CButton::GetImageList](../Topic/CButton::GetImageList.md)|Récupère la liste d'images du contrôle bouton.|  
|[CButton::GetNote](../Topic/CButton::GetNote.md)|Récupère le composant de remarque du contrôle de lien en cours de commande.|  
|[CButton::GetNoteLength](../Topic/CButton::GetNoteLength.md)|Extrait la longueur du texte de remarque pour le contrôle de lien en cours de commande.|  
|[CButton::GetSplitGlyph](../Topic/CButton::GetSplitGlyph.md)|Récupère le glyphe associé au contrôle actuel de bouton partagé.|  
|[CButton::GetSplitImageList](../Topic/CButton::GetSplitImageList.md)|Récupère la liste d'images du contrôle actuel de bouton partagé.|  
|[CButton::GetSplitInfo](../Topic/CButton::GetSplitInfo.md)|Récupère les informations qui définissent le contrôle actuel de bouton partagé.|  
|[CButton::GetSplitSize](../Topic/CButton::GetSplitSize.md)|Récupère le rectangle englobant du composant déroulant du contrôle actuel de bouton partagé.|  
|[CButton::GetSplitStyle](../Topic/CButton::GetSplitStyle.md)|Récupère les styles de bouton partagé qui définissent le contrôle actuel de bouton partagé.|  
|[CButton::GetState](../Topic/CButton::GetState.md)|Récupère l'état d'activation, l'état de surbrillance, et l'état de focus d'un contrôle bouton.|  
|[CButton::GetTextMargin](../Topic/CButton::GetTextMargin.md)|Extrait la plage de texte du contrôle bouton.|  
|[CButton::SetBitmap](../Topic/CButton::SetBitmap.md)|Spécifie une bitmap à afficher sur le bouton.|  
|[CButton::SetButtonStyle](../Topic/CButton::SetButtonStyle.md)|Modifie le style d'un bouton.|  
|[CButton::SetCheck](../Topic/CButton::SetCheck.md)|Définit l'état d'activation d'un contrôle bouton.|  
|[CButton::SetCursor](../Topic/CButton::SetCursor.md)|Spécifie une image de curseur à afficher sur le bouton.|  
|[CButton::SetDropDownState](../Topic/CButton::SetDropDownState.md)|Définit l'état déroulant du contrôle actuel de bouton partagé.|  
|[CButton::SetIcon](../Topic/CButton::SetIcon.md)|Spécifie une icône à afficher sur le bouton.|  
|[CButton::SetImageList](../Topic/CButton::SetImageList.md)|Définit la liste d'images du contrôle bouton.|  
|[CButton::SetNote](../Topic/CButton::SetNote.md)|Définit la remarque sur le contrôle de lien en cours de commande.|  
|[CButton::SetSplitGlyph](../Topic/CButton::SetSplitGlyph.md)|Associe un glyphe spécifié avec le contrôle actuel de bouton partagé.|  
|[CButton::SetSplitImageList](../Topic/CButton::SetSplitImageList.md)|Associe une liste d'images avec le contrôle actuel de bouton partagé.|  
|[CButton::SetSplitInfo](../Topic/CButton::SetSplitInfo.md)|Spécifie les informations qui définissent le contrôle actuel de bouton partagé.|  
|[CButton::SetSplitSize](../Topic/CButton::SetSplitSize.md)|Définit le rectangle englobant du composant déroulant du contrôle actuel de bouton partagé.|  
|[CButton::SetSplitStyle](../Topic/CButton::SetSplitStyle.md)|Définit le style du contrôle actuel de bouton partagé.|  
|[CButton::SetState](../Topic/CButton::SetState.md)|Définit l'état de mise en surbrillance d'un contrôle bouton.|  
|[CButton::SetTextMargin](../Topic/CButton::SetTextMargin.md)|Définit la plage de texte du contrôle bouton.|  
  
## Notes  
 Un contrôle bouton est une petite, rectangulaire fenêtre enfant qui peut être un clic de démarrer et d'arrêt.  Les boutons peuvent être utilisés unique ou aux groupes et peuvent être étiquetés ou apparus sans texte.  Un bouton change en général l'apparence lorsque l'utilisateur clique dessus.  
  
 Les boutons classiques sont la case à cocher, la case d'option, puis le bouton poussoir.  Un objet d' `CButton` peut devenir l'un de ces, selon [style de boutons](../../mfc/reference/button-styles.md) spécifié à son initialisation par la fonction membre de [Create](../Topic/CButton::Create.md) .  
  
 En outre, la classe de [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) dérivée d' `CButton` charge la création de contrôles bouton étiquetés avec des images bitmap au lieu du texte.  `CBitmapButton` peut avoir des bitmaps distinctes pour un bouton, vers le bas, le focus, et les rapports désactivés.  
  
 Vous pouvez créer un contrôle bouton d'un modèle de boîte de dialogue ou directement dans votre code.  Dans les deux cas, abord appeler le constructeur `CButton` pour construire l'objet d' `CButton` ; appelez la fonction membre de **Créer** pour créer le contrôle bouton windows et le lier à l'objet d' `CButton` .  
  
 La construction peut être un processus à une étape dans une classe dérivée d' `CButton`.  Entrez un constructeur pour la classe dérivée et appelez **Créer** du constructeur.  
  
 Si vous souhaitez gérer des messages de notification de fenêtres envoyés par un contrôle bouton à son parent \(généralement une classe dérivée de [CDialog](../../mfc/reference/cdialog-class.md)\), ajoutez une entrée de la table des messages et une fonction membre gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de la table des messages prend la forme suivante :  
  
 Notification**\(**`id`, `memberFxn`**\)**d'**ON\_**  
  
 où `id` spécifie l'ID de fenêtre enfant de l'émission de contrôle la notification et `memberFxn` est le nom de la fonction membre parente que vous avez écrit pour traiter la notification.  
  
 Le prototype de fonction du parent est la suivante :  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Les entrées de la table des messages potentielles sont les suivantes :  
  
|Entrée de mappage|Envoyé au parent lorsque…|  
|-----------------------|-------------------------------|  
|**ON\_BN\_CLICKED**|l'utilisateur clique sur un bouton.|  
|**ON\_BN\_DOUBLECLICKED**|L'utilisateur double\-clique sur un bouton.|  
  
 Si vous créez un objet d' `CButton` d'une ressource de boîte de dialogue, l'objet d' `CButton` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CButton` dans une fenêtre, vous devrez peut\-être la destruction.  Si vous créez l'objet d' `CButton` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque l'utilisateur ferme le contrôle bouton windows.  Si vous créez l'objet d' `CButton` sur la pile, ou elle est incorporée dans l'objet dialog parent, elle est perdue automatiquement.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton Class](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)