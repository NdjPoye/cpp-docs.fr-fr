---
title: "CMFCToolBarInfo Class | Microsoft Docs"
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
  - "CMFCToolBarInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarInfo class"
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contient les ID de ressource des images de barre d'outils dans différents états.  `CMFCToolBarInfo` est une classe d'assistance utilisée comme paramètre de la méthode de [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md) .  
  
## Syntaxe  
  
```  
class CMFCToolBarInfo  
```  
  
## Membres  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarInfo::m\_uiColdResID](../Topic/CMFCToolBarInfo::m_uiColdResID.md)|ID de ressource de la bitmap de barre d'outils qui contient des images \(froides\) normales de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiDisabledResID](../Topic/CMFCToolBarInfo::m_uiDisabledResID.md)|ID de ressource de la bitmap de barre d'outils qui contient des images désactivées de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiHotResID](../Topic/CMFCToolBarInfo::m_uiHotResID.md)|ID de ressource de la bitmap de barre d'outils qui contient des images \(chaudes\) sélectionnées de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiLargeColdResID](../Topic/CMFCToolBarInfo::m_uiLargeColdResID.md)|ID de ressource de la bitmap de barre d'outils qui contient de grandes, images normales de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiLargeDisabledResID](../Topic/CMFCToolBarInfo::m_uiLargeDisabledResID.md)|ID de ressource de la bitmap de barre d'outils qui contient de grandes, désactivées images de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiLargeHotResID](../Topic/CMFCToolBarInfo::m_uiLargeHotResID.md)|ID de ressource de la bitmap de barre d'outils qui contient de grandes, sélectionnées images de barre d'outils.|  
|[CMFCToolBarInfo::m\_uiMenuDisabledResID](../Topic/CMFCToolBarInfo::m_uiMenuDisabledResID.md)|ID de ressource de la bitmap de barre d'outils qui contient des images désactivées de menu.|  
|[CMFCToolBarInfo::m\_uiMenuResID](../Topic/CMFCToolBarInfo::m_uiMenuResID.md)|ID de ressource de la bitmap de barre d'outils qui contient des images de menu.|  
  
## Notes  
 Une bitmap complète de barre d'outils se compose de petites images de barre d'outils \(boutons\) d'une taille fixe.  Chaque ID de ressource qui est stocké dans un objet d' `CMFCToolBarInfo` est une bitmap qui contient un jeu complet des images de barre d'outils dans un état unique \(par exemple, les images sélectionné, désactivé, grandes, ou de menu\).  
  
## Hiérarchie d'héritage  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## Configuration requise  
 **en\-tête :** afxtoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)