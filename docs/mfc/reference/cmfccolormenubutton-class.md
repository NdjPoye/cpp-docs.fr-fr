---
title: "CMFCColorMenuButton Class | Microsoft Docs"
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
  - "CMFCColorMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorMenuButton class"
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCColorMenuButton` prend en charge une commande de menu ou un bouton de barre d'outils qui démarre une boîte de dialogue du sélecteur de couleurs.  
  
## Syntaxe  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](../Topic/CMFCColorMenuButton::CMFCColorMenuButton.md)|Construit un objet `CMFCColorMenuButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](../Topic/CMFCColorMenuButton::EnableAutomaticButton.md)|Active et désactive un bouton « automatique » qui est positionnée au\-dessus de les boutons normaux de couleur.  \(Le bouton automatique du système standard est étiqueté **Automatique**.\)|  
|[CMFCColorMenuButton::EnableDocumentColors](../Topic/CMFCColorMenuButton::EnableDocumentColors.md)|Active l'affichage de couleurs de document spécifique au lieu des couleurs système.|  
|[CMFCColorMenuButton::EnableOtherButton](../Topic/CMFCColorMenuButton::EnableOtherButton.md)|Active et désactive un « autre » bouton qui est positionné sous les boutons normaux de couleur.  \(Le système standard « autre » bouton est étiqueté **Plus les couleurs…**.\)|  
|[CMFCColorMenuButton::EnableTearOff](../Topic/CMFCColorMenuButton::EnableTearOff.md)|Active la capacité d'arracher un volet de couleur.|  
|[CMFCColorMenuButton::GetAutomaticColor](../Topic/CMFCColorMenuButton::GetAutomaticColor.md)|Extrait la couleur automatique actuelle.|  
|[CMFCColorMenuButton::GetColor](../Topic/CMFCColorMenuButton::GetColor.md)|Extrait la couleur du bouton actuel.|  
|[CMFCColorMenuButton::GetColorByCmdID](../Topic/CMFCColorMenuButton::GetColorByCmdID.md)|Extrait la couleur qui correspond à un ID de commande spécifiée|  
|[CMFCColorMenuButton::OnChangeParentWnd](../Topic/CMFCColorMenuButton::OnChangeParentWnd.md)|Appelé par l'infrastructure lorsque la fenêtre parente change.|  
|[CMFCColorMenuButton::OpenColorDialog](../Topic/CMFCColorMenuButton::OpenColorDialog.md)|Ouvre une boîte de dialogue de sélection de couleurs.|  
|[CMFCColorMenuButton::SetColor](../Topic/CMFCColorMenuButton::SetColor.md)|Définit la couleur du bouton en cours de couleur.|  
|[CMFCColorMenuButton::SetColorByCmdID](../Topic/CMFCColorMenuButton::SetColorByCmdID.md)|Définit la couleur du bouton de menu spécifié de couleur.|  
|[CMFCColorMenuButton::SetColorName](../Topic/CMFCColorMenuButton::SetColorName.md)|Définit un nouveau nom pour la couleur spécifiée.|  
|[CMFCColorMenuButton::SetColumnsNumber](../Topic/CMFCColorMenuButton::SetColumnsNumber.md)|Définit le nombre de colonnes affichées par un objet d' `CMFCColorBar` .|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](../Topic/CMFCColorMenuButton::CopyFrom.md)|Copie un autre bouton de barre d'outils sur le bouton actuel.|  
|[CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)|Crée une boîte de dialogue du sélecteur de couleurs.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](../Topic/CMFCColorMenuButton::IsEmptyMenuAllowed.md)|Indique si les menus vides sont pris en charge.|  
|[CMFCColorMenuButton::OnDraw](../Topic/CMFCColorMenuButton::OnDraw.md)|Appelé par l'infrastructure pour afficher une image sur un bouton.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](../Topic/CMFCColorMenuButton::OnDrawOnCustomizeList.md)|Appelé par l'infrastructure avant qu'un objet d' `CMFCColorMenuButton` soit affiché dans la liste d'une boîte de dialogue personnalisation de la barre d'outils.|  
  
## Notes  
 Pour remplacer la commande de menu ou le bouton de barre d'outils d'origine par un objet d' `CMFCColorMenuButton` , créez l'objet d' `CMFCColorMenuButton` , définissez les styles appropriés de [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) , puis appelez la méthode d' `ReplaceButton` de classe de [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) .  Si vous personnalisez une barre d'outils, appelez la méthode de [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) .  
  
 La boîte de dialogue du sélecteur de couleurs est créée au cours de le traitement du gestionnaire d'événements de [CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md) .  Le gestionnaire d'événement informe le frame parent avec un message d' `WM_COMMAND` .  L'objet d' `CMFCColorMenuButton` envoie l'ID du contrôle qui est assigné à la commande de menu ou sur le bouton de barre d'outils d'origine.  
  
## Exemple  
 L'exemple suivant montre comment créer et configurer un bouton de menu de couleur en utilisant différentes méthodes dans la classe d' `CMFCColorMenuButton` .  Dans l'exemple, un objet d' `CPalette` est d'abord créé et ensuite utilisé pour construire un objet avec de la classe d' `CMFCColorMenuButton` .  L'objet d' `CMFCColorMenuButton` est ensuite configuré en activant ses boutons automatiques et autres, et en définissant sa couleur et le nombre de colonnes.  Ce code fait partie d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/CPP/cmfccolormenubutton-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcolormenubutton.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)