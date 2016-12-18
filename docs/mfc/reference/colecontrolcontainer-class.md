---
title: "COleControlContainer Class | Microsoft Docs"
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
  - "COleControlContainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs de contrôles ActiveX (C++), control site"
  - "COleControlContainer class"
  - "contrôles personnalisés (MFC), sites"
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleControlContainer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Agit comme un conteneur de contrôle des contrôles ActiveX.  
  
## Syntaxe  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlContainer::COleControlContainer](../Topic/COleControlContainer::COleControlContainer.md)|Construit un objet `COleControlContainer`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlContainer::AttachControlSite](../Topic/COleControlContainer::AttachControlSite.md)|Crée un site de contrôle, il est hébergé par le conteneur.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](../Topic/COleControlContainer::BroadcastAmbientPropertyChange.md)|Signale à tous les contrôles hébergés qu'une propriété ambiante a changé.|  
|[COleControlContainer::CheckDlgButton](../Topic/COleControlContainer::CheckDlgButton.md)|Modifie le contrôle button spécifié.|  
|[COleControlContainer::CheckRadioButton](../Topic/COleControlContainer::CheckRadioButton.md)|Active la case d'option spécifiée d'un groupe.|  
|[COleControlContainer::CreateControl](../Topic/COleControlContainer::CreateControl.md)|Crée un contrôle ActiveX hébergé.|  
|[COleControlContainer::CreateOleFont](../Topic/COleControlContainer::CreateOleFont.md)|Crée une police OLE.|  
|[COleControlContainer::FindItem](../Topic/COleControlContainer::FindItem.md)|Retourne le site personnalisé du contrôle spécifié.|  
|[COleControlContainer::FreezeAllEvents](../Topic/COleControlContainer::FreezeAllEvents.md)|Détermine si le site de contrôle accepte des événements.|  
|[COleControlContainer::GetAmbientProp](../Topic/COleControlContainer::GetAmbientProp.md)|Récupère la propriété ambiante spécifiée.|  
|[COleControlContainer::GetDlgItem](../Topic/COleControlContainer::GetDlgItem.md)|Récupère le contrôle de boîte de dialogue spécifié.|  
|[COleControlContainer::GetDlgItemInt](../Topic/COleControlContainer::GetDlgItemInt.md)|Récupère la valeur du contrôle de boîte de dialogue spécifié.|  
|[COleControlContainer::GetDlgItemText](../Topic/COleControlContainer::GetDlgItemText.md)|Extrait la légende du contrôle de boîte de dialogue spécifié.|  
|[COleControlContainer::HandleSetFocus](../Topic/COleControlContainer::HandleSetFocus.md)|Détermine si le conteneur gère les messages d' `WM_SETFOCUS` .|  
|[COleControlContainer::HandleWindowlessMessage](../Topic/COleControlContainer::HandleWindowlessMessage.md)|Gère les messages envoyés à un contrôle sans fenêtre.|  
|[COleControlContainer::IsDlgButtonChecked](../Topic/COleControlContainer::IsDlgButtonChecked.md)|Détermine l'état du bouton spécifié.|  
|[COleControlContainer::OnPaint](../Topic/COleControlContainer::OnPaint.md)|Appelé pour redessiner une partie du conteneur.|  
|[COleControlContainer::OnUIActivate](../Topic/COleControlContainer::OnUIActivate.md)|Appelé lorsqu'un contrôle sur pour être visuelle est activé.|  
|[COleControlContainer::OnUIDeactivate](../Topic/COleControlContainer::OnUIDeactivate.md)|Appelé lorsqu'un contrôle est sur le point d'être désactivé.|  
|[COleControlContainer::ScrollChildren](../Topic/COleControlContainer::ScrollChildren.md)|Appelé par l'infrastructure lorsque des messages de défilement sont acceptés d'une fenêtre enfant.|  
|[COleControlContainer::SendDlgItemMessage](../Topic/COleControlContainer::SendDlgItemMessage.md)|Envoie un message au contrôle spécifié.|  
|[COleControlContainer::SetDlgItemInt](../Topic/COleControlContainer::SetDlgItemInt.md)|Définit la valeur du contrôle spécifié.|  
|[COleControlContainer::SetDlgItemText](../Topic/COleControlContainer::SetDlgItemText.md)|Définit le texte du contrôle spécifié.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlContainer::m\_crBack](../Topic/COleControlContainer::m_crBack.md)|La couleur d'arrière\-plan du conteneur.|  
|[COleControlContainer::m\_crFore](../Topic/COleControlContainer::m_crFore.md)|La couleur de premier plan du conteneur.|  
|[COleControlContainer::m\_listSitesOrWnds](../Topic/COleControlContainer::m_listSitesOrWnds.md)|Une liste des sites de contrôle pris en charge.|  
|[COleControlContainer::m\_nWindowlessControls](../Topic/COleControlContainer::m_nWindowlessControls.md)|Le nombre de contrôles sans fenêtre hébergés.|  
|[COleControlContainer::m\_pOleFont](../Topic/COleControlContainer::m_pOleFont.md)|Un pointeur vers OLE police du site de contrôle personnalisé.|  
|[COleControlContainer::m\_pSiteCapture](../Topic/COleControlContainer::m_pSiteCapture.md)|Pointeur vers le site de contrôle de capture.|  
|[COleControlContainer::m\_pSiteFocus](../Topic/COleControlContainer::m_pSiteFocus.md)|Pointeur vers le contrôle qui a actuellement le focus d'entrée.|  
|[COleControlContainer::m\_pSiteUIActive](../Topic/COleControlContainer::m_pSiteUIActive.md)|Pointeur vers le contrôle qui est actuellement sur place activé.|  
|[COleControlContainer::m\_pWnd](../Topic/COleControlContainer::m_pWnd.md)|Pointeur vers la fenêtre implémentant le conteneur de contrôle.|  
|[COleControlContainer::m\_siteMap](../Topic/COleControlContainer::m_siteMap.md)|Le plan de site.|  
  
## Notes  
 Cela est fait en fournissant la prise en charge pour un ou plusieurs sites de contrôle ActiveX \(implémentés par `COleControlSite`\).  `COleControlContainer` entièrement implémente les interfaces d' [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) et d' [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) , permettant aux contrôles ActiveX contenus pour accomplir les compétences en tant qu'éléments sur place.  
  
 En général, cette classe est utilisée conjointement avec `COccManager` et `COleControlSite` pour implémenter un conteneur de contrôles ActiveX personnalisé, avec les sites personnalisés pour un ou plusieurs contrôles ActiveX.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## Configuration requise  
 **Header:** afxocc.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager Class](../../mfc/reference/coccmanager-class.md)