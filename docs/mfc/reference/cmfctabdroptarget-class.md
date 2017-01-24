---
title: "CMFCTabDropTarget Class | Microsoft Docs"
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
  - "CMFCTabDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabDropTarget class"
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTabDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un mécanisme de communication entre un contrôle onglet et OLE les bibliothèques.  
  
## Syntaxe  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCTabDropTarget::OnDragEnter](../Topic/CMFCTabDropTarget::OnDragEnter.md)|Appelé par l'infrastructure lorsque l'utilisateur fait glisser un objet dans une fenêtre d'onglet.  \(Substitutions [COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md).\)|  
|[CMFCTabDropTarget::OnDragLeave](../Topic/CMFCTabDropTarget::OnDragLeave.md)|Appelé par l'infrastructure lorsque l'utilisateur fait glisser un objet hors de la fenêtre d'onglet qui a le focus.  \(Substitutions [COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md).\)|  
|[CMFCTabDropTarget::OnDragOver](../Topic/CMFCTabDropTarget::OnDragOver.md)|Appelé par l'infrastructure lorsque l'utilisateur fait glisser un objet dans la fenêtre d'onglet qui a le focus.  \(Substitutions [COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md).\)|  
|[CMFCTabDropTarget::OnDropEx](../Topic/CMFCTabDropTarget::OnDropEx.md)|Appelé par l'infrastructure lorsque l'utilisateur relâche le bouton de la souris vers la fin d'une opération glisser.  \(Substitutions [COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md).\)|  
|[CMFCTabDropTarget::Register](../Topic/CMFCTabDropTarget::Register.md)|Stocke le contrôle comme un qui peut être la cible d'une opération de glisser\-déplacer OLE.|  
  
### Remarques  
 Cette classe fournit la prise en charge du glisser\-déplacer dans la classe d' `CMFCBaseTabCtrl` .  Si votre application initialise les bibliothèques OLE à l'aide de [AfxOleInit](../Topic/AfxOleInit.md) fonctionnent, des objets d' `CMFCBaseTabCtrl` s'inscrivent pour les opérations de glisser\-déplacer.  
  
 La classe d' `CMFCTabDropTarget` étend sa classe de base en effectuant l'onglet sous le curseur lorsqu'une opération de glissement se produit actif.  Pour plus d'informations sur les opérations de glisser\-déplacer, consultez [Glisser\-déplacer OLE \(\)](../../mfc/drag-and-drop-ole.md).  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCTabDropTarget` et utiliser sa méthode d' `Register` .  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/CPP/cmfctabdroptarget-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## Configuration requise  
 **en\-tête :** afxbasetabctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Glisser\-déplacer OLE \(\)](../../mfc/drag-and-drop-ole.md)