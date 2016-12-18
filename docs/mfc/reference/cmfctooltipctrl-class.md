---
title: "CMFCToolTipCtrl Class | Microsoft Docs"
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
  - "CMFCToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipCtrl class"
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémentation d'info\-bulle étendue basée sur la [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md).  Une info\-bulle basée sur la classe `CMFCToolTipCtrl` peut afficher une icône, une étiquette et une description.  Vous pouvez personnaliser son apparence visuelle en utilisant un dégradé, un texte personnalisé et des couleurs de bordure, un texte en gras, des angles arrondis ou un style d'info\-bulle.  
  
## Syntaxe  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Constructeur par défaut.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolTipCtrl::GetIconSize](../Topic/CMFCToolTipCtrl::GetIconSize.md)|Retourne la taille d'une icône dans une info\-bulle.|  
|[CMFCToolTipCtrl::GetParams](../Topic/CMFCToolTipCtrl::GetParams.md)|Retourne les paramètres d'affichage d'une info\-bulle.|  
|[CMFCToolTipCtrl::OnDrawBorder](../Topic/CMFCToolTipCtrl::OnDrawBorder.md)|Dessine la bordure d'une info\-bulle.|  
|[CMFCToolTipCtrl::OnDrawDescription](../Topic/CMFCToolTipCtrl::OnDrawDescription.md)||  
|[CMFCToolTipCtrl::OnDrawIcon](../Topic/CMFCToolTipCtrl::OnDrawIcon.md)|Affiche une icône dans une info\-bulle.|  
|[CMFCToolTipCtrl::OnDrawLabel](../Topic/CMFCToolTipCtrl::OnDrawLabel.md)|Dessine l'étiquette d'une info\-bulle ou calcule la taille de l'étiquette.|  
|[CMFCToolTipCtrl::OnDrawSeparator](../Topic/CMFCToolTipCtrl::OnDrawSeparator.md)|Dessine le séparateur entre l'étiquette et la description dans une info\-bulle.|  
|[CMFCToolTipCtrl::OnFillBackground](../Topic/CMFCToolTipCtrl::OnFillBackground.md)|Remplit l'arrière\-plan de l'info\-bulle.|  
|[CMFCToolTipCtrl::SetDescription](../Topic/CMFCToolTipCtrl::SetDescription.md)|Définit la description affichée par l'info\-bulle.|  
|[CMFCToolTipCtrl::SetFixedWidth](../Topic/CMFCToolTipCtrl::SetFixedWidth.md)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](../Topic/CMFCToolTipCtrl::SetHotRibbonButton.md)||  
|[CMFCToolTipCtrl::SetLocation](../Topic/CMFCToolTipCtrl::SetLocation.md)||  
|[CMFCToolTipCtrl::SetParams](../Topic/CMFCToolTipCtrl::SetParams.md)|Spécifie l'apparence visuelle d'une info\-bulle en utilisant un objet `CMFCToolTipInfo`.|  
  
## Notes  
 Utilisez conjointement les objets `CMFCToolTipCtrl`, `CMFCToolTipInfo` et [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md) pour implémenter des info\-bulles personnalisées dans votre application.  
  
 Par exemple, pour utiliser des info\-bulles en forme de bulle, procédez comme suit :  
  
 1.  Utilisez la méthode [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) pour initialiser le gestionnaire d'info\-bulles dans votre application.  
  
 2.  Créez une structure `CMFCToolTipInfo` pour spécifier le style visuel souhaité :  
  
```  
CMFCToolTipInfo params;  
 params.m_bBoldLabel = FALSE;  
 params.m_bDrawDescription = FALSE;  
 params.m_bDrawIcon = FALSE;  
 params.m_bRoundedCorners = TRUE;  
 params.m_bDrawSeparator = FALSE;  
 if (m_bCustomColors)  
 {  
  params.m_clrFill = RGB (255, 255, 255);  
  params.m_clrFillGradient = RGB (228, 228, 240);  
  params.m_clrText = RGB (61, 83, 80);  
  params.m_clrBorder = RGB (144, 149, 168);  
 }  
```  
  
 3.  Utilisez la méthode [CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md) pour définir le style visuel de toutes les info\-bulles de l'application en utilisant les styles définis dans l'objet `CMFCToolTipInfo` :  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);  
```  
  
 Vous pouvez aussi faire dériver une nouvelle classe de `CMFCToolTipCtrl` pour contrôler le comportement et le rendu des info\-bulles.  Pour spécifier une nouvelle classe de contrôle d'info\-bulle, utilisez la méthode `CTooltipManager::SetTooltipParams` :  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
  
 Pour restaurer la classe de contrôle d'info\-bulle par défaut et rétablir l'état par défaut de l'apparence des info\-bulles, spécifiez la valeur NULL dans les paramètres de classe Runtime et d'informations sur les info\-bulles dans `SetTooltipParams` :  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL, NULL);  
```  
  
## Exemple  
 L'exemple suivant montre comment construire un objet `CMFCToolTipCtrl`, définir la description affichée par l'info\-bulle et définir la largeur du contrôle info\-bulle.  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/CPP/cmfctooltipctrl-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## Configuration requise  
 **En\-tête :** afxtooltipctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)