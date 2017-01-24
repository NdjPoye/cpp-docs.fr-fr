---
title: "CMFCRibbonLinkCtrl Class | Microsoft Docs"
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
  - "CMFCRibbonLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonLinkCtrl class"
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un lien hypertexte qui est positionné sur un ruban.  Le lien hypertexte ouvre une page Web lorsque vous cliquez dessus.  
  
## Syntaxe  
  
```  
class CMFCRibbonLinkCtrl : public CMFCRibbonButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](../Topic/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl.md)|Construit et initialise un objet `CMFCRibbonLinkCtrl`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonLinkCtrl::CopyFrom](../Topic/CMFCRibbonLinkCtrl::CopyFrom.md)|\(Substitue `CMFCRibbonButton::CopyFrom`.\)|  
|[CMFCRibbonLinkCtrl::GetCompactSize](../Topic/CMFCRibbonLinkCtrl::GetCompactSize.md)|\(Substitue [CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md).\)|  
|[CMFCRibbonLinkCtrl::GetLink](../Topic/CMFCRibbonLinkCtrl::GetLink.md)|Retourne la valeur du lien hypertexte.|  
|[CMFCRibbonLinkCtrl::GetRegularSize](../Topic/CMFCRibbonLinkCtrl::GetRegularSize.md)|\(Substitue [CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md).\)|  
|[CMFCRibbonLinkCtrl::GetToolTipText](../Topic/CMFCRibbonLinkCtrl::GetToolTipText.md)|\(Substitue [CMFCRibbonButton::GetToolTipText](../Topic/CMFCRibbonButton::GetToolTipText.md).\)|  
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](../Topic/CMFCRibbonLinkCtrl::IsDrawTooltipImage.md)|\(Substitue `CMFCRibbonButton::IsDrawTooltipImage`.\)|  
|[CMFCRibbonLinkCtrl::OnDraw](../Topic/CMFCRibbonLinkCtrl::OnDraw.md)|\(Substitue [CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md).\)|  
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](../Topic/CMFCRibbonLinkCtrl::OnDrawMenuImage.md)|\(Substitue [CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md).\)|  
|[CMFCRibbonLinkCtrl::OnMouseMove](../Topic/CMFCRibbonLinkCtrl::OnMouseMove.md)|\(Substitue `CMFCRibbonButton::OnMouseMove`.\)|  
|[CMFCRibbonLinkCtrl::OnSetIcon](../Topic/CMFCRibbonLinkCtrl::OnSetIcon.md)||  
|[CMFCRibbonLinkCtrl::OpenLink](../Topic/CMFCRibbonLinkCtrl::OpenLink.md)|Ouvre la page web spécifiée dans le lien hypertexte.|  
|[CMFCRibbonLinkCtrl::SetLink](../Topic/CMFCRibbonLinkCtrl::SetLink.md)|Définit la valeur du lien hypertexte.|  
  
## Notes  
 Après avoir créé un lien hypertexte, ajoutez\-le à un volet en appelant [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)  
  
## Configuration requise  
 **En\-tête :** afxRibbonLinkCtrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)