---
title: "COleDropTarget Class | Microsoft Docs"
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
  - "COleDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropTarget class"
  - "glisser-déplacer, drop target"
  - "drop commands"
  - "drop commands, accepter"
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un mécanisme de communication entre une fenêtre et OLE les bibliothèques.  
  
## Syntaxe  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDropTarget::COleDropTarget](../Topic/COleDropTarget::COleDropTarget.md)|Construit un objet `COleDropTarget`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md)|Appelé lorsque le curseur entre dans tout d'abord la fenêtre.|  
|[COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md)|Appelé lorsque le curseur est déplacé hors de la fenêtre.|  
|[COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md)|Appelé à plusieurs reprises lorsque le curseur est déplacé sur la fenêtre.|  
|[COleDropTarget::OnDragScroll](../Topic/COleDropTarget::OnDragScroll.md)|Appelé pour déterminer si le curseur est déplacé dans la zone de défilement de la fenêtre.|  
|[COleDropTarget::OnDrop](../Topic/COleDropTarget::OnDrop.md)|Appelée lorsque les données sont supprimées dans la fenêtre, gestionnaire par défaut.|  
|[COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md)|Appelée lorsque les données sont supprimées dans la fenêtre, gestionnaire initial.|  
|[COleDropTarget::Register](../Topic/COleDropTarget::Register.md)|Stocke la fenêtre comme cible de déplacement valide.|  
|[COleDropTarget::Revoke](../Topic/COleDropTarget::Revoke.md)|Pour arrêter la fenêtre d'être une cible de déplacement valide.|  
  
## Notes  
 Créer un objet de cette classe permet à une fenêtre pour recevoir des données via le mécanisme de glisser\-déplacer OLE.  
  
 Pour obtenir une fenêtre pour recevoir des commandes de déplacement, vous devez d'abord créer un objet de la classe d' `COleDropTarget` , puis appelez la fonction de [registre](../Topic/COleDropTarget::Register.md) avec un pointeur vers l'objet souhaité dans `CWnd` comme paramètre unique.  
  
 Pour plus d'informations sur les opérations de glisser\-déplacer en utilisant OLE, consultez l'article [Glisser\-déplacer OLE \(\)](../../mfc/drag-and-drop-ole.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDropSource Class](../../mfc/reference/coledropsource-class.md)