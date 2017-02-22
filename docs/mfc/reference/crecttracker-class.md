---
title: "CRectTracker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRectTracker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker class"
  - "displaying items"
  - "resizing items"
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRectTracker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet un élément à afficher, être déplacé, redimensionné et dans différentes vues.  
  
## Syntaxe  
  
```  
  
class CRectTracker  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRectTracker::CRectTracker](../Topic/CRectTracker::CRectTracker.md)|Construit un objet `CRectTracker`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRectTracker::AdjustRect](../Topic/CRectTracker::AdjustRect.md)|Appelé lorsque le rectangle est redimensionné.|  
|[CRectTracker::Draw](../Topic/CRectTracker::Draw.md)|Affiche le rectangle.|  
|[CRectTracker::DrawTrackerRect](../Topic/CRectTracker::DrawTrackerRect.md)|Appelé lorsque vous dessinez le bord d'un objet d' `CRectTracker` .|  
|[CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)|Appelé pour obtenir le masque les poignées de redimensionnement d'un élément d' `CRectTracker`.|  
|[CRectTracker::GetTrueRect](../Topic/CRectTracker::GetTrueRect.md)|Retourne la largeur et la hauteur du rectangle, y compris les poignées de redimensionnement.|  
|[CRectTracker::HitTest](../Topic/CRectTracker::HitTest.md)|Retourne la position actuelle du curseur en rapport avec l'objet d' `CRectTracker` .|  
|[CRectTracker::NormalizeHit](../Topic/CRectTracker::NormalizeHit.md)|Normalise un code de test de positionnement.|  
|[CRectTracker::OnChangedRect](../Topic/CRectTracker::OnChangedRect.md)|Appelé lorsque le rectangle a été redimensionné ou déplacé.|  
|[CRectTracker::SetCursor](../Topic/CRectTracker::SetCursor.md)|Place le curseur, selon sa position sur le rectangle.|  
|[CRectTracker::Track](../Topic/CRectTracker::Track.md)|Permet à l'utilisateur de manipuler le rectangle.|  
|[CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)|Permet à l'utilisateur à « caoutchouc\- bande » la sélection.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRectTracker::m\_nHandleSize](../Topic/CRectTracker::m_nHandleSize.md)|Détermine la taille des poignées de redimensionnement.|  
|[CRectTracker::m\_nStyle](../Topic/CRectTracker::m_nStyle.md)|Styles actuels du dispositif de suivi.|  
|[CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)|Position actuelle \(en pixels\) du rectangle.|  
|[CRectTracker::m\_sizeMin](../Topic/CRectTracker::m_sizeMin.md)|Détermine la largeur et la hauteur minimales rectangle.|  
  
## Notes  
 `CRectTracker` n'a pas de classe de base.  
  
 Bien que la classe d' `CRectTracker` est conçue pour permettre à l'utilisateur d'interagir avec OLE éléments à l'aide d'une interface graphique, son utilisation n'est pas limitée aux applications OLE\- activées.  Ce peut être utilisée n'importe où une telle interface utilisateur est requis.  
  
 Les zones d'`CRectTracker` peuvent être pleines ou des lignes discontinues.  L'élément peut être attribué à un de bordure haché ou être recouvert avec un modèle haché pour indiquer différents états de l'élément.  Vous pouvez définir huit poignées de redimensionnement sur la bordure plus éloignée ou à l'intérieur de l'élément.  \(Pour une explication des poignées de redimensionnement, consultez [GetHandleMask](../Topic/CRectTracker::GetHandleMask.md).\) Enfin, `CRectTracker` vous permet de modifier l'orientation d'un élément lors de le redimensionnement.  
  
 Pour utiliser `CRectTracker`, construisez un objet d' `CRectTracker` et le spécifiez qui affichent les rapports sont initialisés.  Vous pouvez ensuite utiliser cette interface pour fournir une aide visuelle à l'utilisateur sur l'état actuel de l'élément OLE associé à l'objet d' `CRectTracker` .  
  
 Pour plus d'informations sur l'utilisation `CRectTracker`, consultez l'article [Mécanismes de traçage](../../mfc/trackers.md).  
  
## Hiérarchie d'héritage  
 `CRectTracker`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [TRACKER d'exemple MFC](../../top/visual-cpp-samples.md)   
 [DRAWCLI exemple MFC](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleResizeBar Class](../../mfc/reference/coleresizebar-class.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)