---
title: "COleDropSource Class | Microsoft Docs"
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
  - "COleDropSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropSource class"
  - "glisser-déplacer, drop source"
  - "opérations glisser"
  - "drop target, dragging data to"
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDropSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet aux données à faire glisser vers une cible de déplacement.  
  
## Syntaxe  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDropSource::COleDropSource](../Topic/COleDropSource::COleDropSource.md)|Construit un objet `COleDropSource`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDropSource::GiveFeedback](../Topic/COleDropSource::GiveFeedback.md)|Modifie le curseur pendant une opération de glisser\-déplacer.|  
|[COleDropSource::OnBeginDrag](../Topic/COleDropSource::OnBeginDrag.md)|Gère la capture de la souris pendant une opération de glisser\-déplacer.|  
|[COleDropSource::QueryContinueDrag](../Topic/COleDropSource::QueryContinueDrag.md)|Vérifie que faire glisser doit continuer.|  
  
## Notes  
 La classe de [COleDropTarget](../../mfc/reference/coledroptarget-class.md) gère la partie la réception de l'opération de glisser\-déplacer.  L'objet d' `COleDropSource` est chargé de déterminer si une opération de glissement démarre, de fournir des commentaires pendant l'opération de glissement, et de le déterminer si l'opération de glissement se termine.  
  
 Pour utiliser un objet d' `COleDropSource` , appelez simplement le constructeur.  Cela simplifie le processus de déterminer quels événements, tels qu'un clic de souris, démarrez une opération glisser à l'aide de la fonction de [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md), de [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md), ou de [COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md) .  Ces fonctions créeront un objet d' `COleDropSource` pour vous.  Vous pouvez modifier le comportement par défaut des fonctions substituables d' `COleDropSource` .  Ces fonctions membres sont appelées aux temps appropriés par l'infrastructure.  
  
 Pour plus d'informations sur les opérations de glisser\-déplacer en utilisant OLE, consultez l'article [Glisser\-déplacer OLE \(\)](../../mfc/drag-and-drop-ole.md).  
  
 Pour plus d'informations, consultez l' [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)