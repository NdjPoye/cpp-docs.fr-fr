---
title: "CRecentDockSiteInfo Class | Microsoft Docs"
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
  - "CRecentDockSiteInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentDockSiteInfo class"
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecentDockSiteInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CRecentDockSiteInfo` est une classe d'assistance qui stocke des informations d'état récentes pour la [CPane Class](../../mfc/reference/cpane-class.md).  
  
## Syntaxe  
  
```  
class CRecentDockSiteInfo : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|Constructeur par défaut.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecentDockSiteInfo::CleanUp](../Topic/CRecentDockSiteInfo::CleanUp.md)||  
|[CRecentDockSiteInfo::GetRecentDefaultPaneDivider](../Topic/CRecentDockSiteInfo::GetRecentDefaultPaneDivider.md)||  
|[CRecentDockSiteInfo::GetRecentDockedPercent](../Topic/CRecentDockSiteInfo::GetRecentDockedPercent.md)||  
|[CRecentDockSiteInfo::GetRecentDockedRect](../Topic/CRecentDockSiteInfo::GetRecentDockedRect.md)||  
|[CRecentDockSiteInfo::GetRecentListOfPanes](../Topic/CRecentDockSiteInfo::GetRecentListOfPanes.md)||  
|[CRecentDockSiteInfo::GetRecentPaneContainer](../Topic/CRecentDockSiteInfo::GetRecentPaneContainer.md)||  
|[CRecentDockSiteInfo::GetRecentTabContainer](../Topic/CRecentDockSiteInfo::GetRecentTabContainer.md)||  
|[CRecentDockSiteInfo::Init](../Topic/CRecentDockSiteInfo::Init.md)||  
|[CRecentDockSiteInfo::IsRecentLeftPane](../Topic/CRecentDockSiteInfo::IsRecentLeftPane.md)||  
|[CRecentDockSiteInfo::operator \=](../Topic/CRecentDockSiteInfo::operator%20=.md)||  
|[CRecentDockSiteInfo::SaveListOfRecentPanes](../Topic/CRecentDockSiteInfo::SaveListOfRecentPanes.md)||  
|[CRecentDockSiteInfo::SetInfo](../Topic/CRecentDockSiteInfo::SetInfo.md)||  
|[CRecentDockSiteInfo::StoreDockInfo](../Topic/CRecentDockSiteInfo::StoreDockInfo.md)||  
  
## Notes  
 `CRecentDockSiteInfo` est une classe de gestion de données.  Elle suit le dernier état d'un `CPane` au fil de ses transitions entre les états ancré et flottant.  Quand un utilisateur double\-clique sur un volet ancrable flottant, il devient ancré.  Un double\-clic sur le volet ancré rétablit ses emplacement, taille et état précédents.  De même, quand le volet est à nouveau ancré, il retrouve son emplacement d'ancrage précédent.  Telles sont les possibilités offertes par cette classe de données.  Comme les membres de cette classe stockent les informations d'état du volet ancré, ils ne doivent pas être directement modifiés par votre application.  
  
 Un objet `CRecentDockSiteInfo` est créé à chaque création d'un volet.  Chaque objet `CPane` dispose d'une variable membre, [CPane::m\_recentDockInfo](../Topic/CPane::m_recentDockInfo.md), pour stocker ces informations.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrecentDockSiteInfo.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)