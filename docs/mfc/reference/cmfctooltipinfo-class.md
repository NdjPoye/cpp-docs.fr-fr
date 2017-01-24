---
title: "CMFCToolTipInfo Class | Microsoft Docs"
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
  - "CMFCToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipInfo class"
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolTipInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stocke des informations sur l'apparence visuelle des info\-bulles.  
  
## Syntaxe  
  
```  
class CMFCToolTipInfo  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolTipInfo::operator\=](../Topic/CMFCToolTipInfo::operator=.md)||  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolTipInfo::m\_bBalloonTooltip](../Topic/CMFCToolTipInfo::m_bBalloonTooltip.md)|Variable booléenne qui indique si l'info\-bulle a l'aspect d'une bulle.|  
|[CMFCToolTipInfo::m\_bBoldLabel](../Topic/CMFCToolTipInfo::m_bBoldLabel.md)|Variable booléenne qui indique si les étiquettes d'info\-bulle s'affichent en caractères gras.|  
|[CMFCToolTipInfo::m\_bDrawDescription](../Topic/CMFCToolTipInfo::m_bDrawDescription.md)|Variable booléenne qui indique si l'info\-bulle contient une description.|  
|[CMFCToolTipInfo::m\_bDrawIcon](../Topic/CMFCToolTipInfo::m_bDrawIcon.md)|Variable booléenne qui indique si l'info\-bulle contient une icône.|  
|[CMFCToolTipInfo::m\_bDrawSeparator](../Topic/CMFCToolTipInfo::m_bDrawSeparator.md)|Variable booléenne qui indique si un séparateur s'affiche entre l'étiquette et la description de l'info\-bulle.|  
|[CMFCToolTipInfo::m\_bRoundedCorners](../Topic/CMFCToolTipInfo::m_bRoundedCorners.md)|Variable booléenne qui indique si l'info\-bulle a des angles arrondis.|  
|[CMFCToolTipInfo::m\_bVislManagerTheme](../Topic/CMFCToolTipInfo::m_bVislManagerTheme.md)|Variable booléenne qui indique si l'apparence de l'info\-bulle doit être contrôlée par un gestionnaire visuel \(consultez [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)\).|  
|[CMFCToolTipInfo::m\_clrBorder](../Topic/CMFCToolTipInfo::m_clrBorder.md)|Couleur de la bordure de l'info\-bulle.|  
|[CMFCToolTipInfo::m\_clrFill](../Topic/CMFCToolTipInfo::m_clrFill.md)|Couleur de l'arrière\-plan de l'info\-bulle.|  
|[CMFCToolTipInfo::m\_clrFillGradient](../Topic/CMFCToolTipInfo::m_clrFillGradient.md)|Couleur du dégradé dans l'info\-bulle.|  
|[CMFCToolTipInfo::m\_clrText](../Topic/CMFCToolTipInfo::m_clrText.md)|Couleur du texte de l'info\-bulle.|  
|[CMFCToolTipInfo::m\_nGradientAngle](../Topic/CMFCToolTipInfo::m_nGradientAngle.md)|Angle du dégradé dans l'info\-bulle.|  
|[CMFCToolTipInfo::m\_nMaxDescrWidth](../Topic/CMFCToolTipInfo::m_nMaxDescrWidth.md)|Largeur maximale, en pixels, de la description figurant dans l'info\-bulle.|  
  
## Notes  
 Utilisez conjointement [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` et [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md) pour implémenter des info\-bulles personnalisées dans votre application.  Pour obtenir un exemple d'utilisation de ces classes d'info\-bulle, consultez la rubrique [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md).  
  
## Exemple  
 L'exemple suivant montre comment définir les valeurs des différentes variables membres de la classe `CMFCToolTipInfo`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/CPP/cmfctooltipinfo-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## Configuration requise  
 **En\-tête :** afxtooltipctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)