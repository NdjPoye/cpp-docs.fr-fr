---
title: "CLinkCtrl Class | Microsoft Docs"
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
  - "CLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinkCtrl class"
  - "controls [MFC], liens"
  - "liens (C++), link control"
  - "SysLink control"
  - "pages Web, link control"
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle commun de SysLink windows.  
  
## Syntaxe  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinkCtrl::CLinkCtrl](../Topic/CLinkCtrl::CLinkCtrl.md)|Construit un objet `CLinkCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CLinkCtrl::Create](../Topic/CLinkCtrl::Create.md)|Crée un contrôle de lien et l'attache à un objet d' `CLinkCtrl` .|  
|[CLinkCtrl::CreateEx](../Topic/CLinkCtrl::CreateEx.md)|Crée un contrôle de lien avec les styles étendus et l'attache à un objet d' `CLinkCtrl` .|  
|[CLinkCtrl::GetIdealHeight](../Topic/CLinkCtrl::GetIdealHeight.md)|Extrait la hauteur idéale du contrôle de lien.|  
|[CLinkCtrl::GetIdealSize](../Topic/CLinkCtrl::GetIdealSize.md)|Calcule la hauteur par défaut du texte de lien pour le contrôle de lien actif, selon la largeur spécifiée du lien.|  
|[CLinkCtrl::GetItem](../Topic/CLinkCtrl::GetItem.md)|Récupère les rapports et les attributs d'un élément de contrôle de lien.|  
|[CLinkCtrl::GetItemID](../Topic/CLinkCtrl::GetItemID.md)|Extrait l'ID d'un élément de contrôle de lien.|  
|[CLinkCtrl::GetItemState](../Topic/CLinkCtrl::GetItemState.md)|Récupère l'état de l'élément du contrôle de lien.|  
|[CLinkCtrl::GetItemUrl](../Topic/CLinkCtrl::GetItemUrl.md)|Récupère l'URL représenté par l'élément du contrôle de lien.|  
|[CLinkCtrl::HitTest](../Topic/CLinkCtrl::HitTest.md)|Détermine si l'utilisateur a cliqué sur le lien spécifié.|  
|[CLinkCtrl::SetItem](../Topic/CLinkCtrl::SetItem.md)|Définit les rapports et les attributs d'un élément de contrôle de lien.|  
|[CLinkCtrl::SetItemID](../Topic/CLinkCtrl::SetItemID.md)|Définit l'ID d'un élément de contrôle de lien.|  
|[CLinkCtrl::SetItemState](../Topic/CLinkCtrl::SetItemState.md)|Définit l'état de l'élément du contrôle de lien.|  
|[CLinkCtrl::SetItemUrl](../Topic/CLinkCtrl::SetItemUrl.md)|Définit l'URL représenté par l'élément du contrôle de lien.|  
  
## Notes  
 Un « contrôle de lien » offre un moyen pratique d'inclure des liens hypertexte dans une fenêtre.  Le contrôle réel est une fenêtre qui affiche le texte balisé et active les applications appropriées lorsque l'utilisateur clique sur un lien inline.  Plusieurs liens sont pris en charge dans l'un contrôle et sont accessibles par un index de base zéro.  
  
 Ce contrôle \(et par conséquent la classe d' `CLinkCtrl` \) est disponible uniquement aux programmes s'exécutant sous Windows XP et versions ultérieures.  
  
 Pour plus d'informations, consultez [contrôle de SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)