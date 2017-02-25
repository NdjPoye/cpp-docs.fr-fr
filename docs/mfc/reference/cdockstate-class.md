---
title: "CDockState Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockState class"
  - "dock state"
  - "docking control bars"
  - "docking tool windows"
  - "position, control bar"
  - "taille"
  - "taille, control bar"
  - "états, dockable control bar"
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDockState Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe sérialisée d' `CObject` qui charge, décharge, ou désactive l'état d'un ou plusieurs barres de contrôles d'ancrage en mémoire persistant \(fichier\).  
  
## Syntaxe  
  
```  
class CDockState : public CObject  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockState::Clear](../Topic/CDockState::Clear.md)|Efface les informations d'état d'ancrage.|  
|[CDockState::GetVersion](../Topic/CDockState::GetVersion.md)|Récupère le numéro de version de l'état stocké de barre.|  
|[CDockState::LoadState](../Topic/CDockState::LoadState.md)|Récupère les informations d'état du Registre ou le fichier .ini.|  
|[CDockState::SaveState](../Topic/CDockState::SaveState.md)|Enregistre les informations d'état au Registre ou au fichier INI.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockState::m\_arrBarInfo](../Topic/CDockState::m_arrBarInfo.md)|Tableau de pointeurs vers des informations d'état stockées d'ancrage avec une entrée pour chaque barre de contrôles.|  
  
## Notes  
 L'état d'ancrage inclut la taille et la position de la barre et si elle est ancrée.  En récupérant l'état stocké d'ancrage, `CDockState` contrôle la position et, si la barre n'est pas visible avec les paramètres actuels d'écran, `CDockState` de la barre mesure la position de la barre de sorte qu'elle soit visible.  L'objectif principal d' `CDockState` est de stocker l'état entier de plusieurs barres de contrôles et de permettre ce rapport à l'enregistrement et le chargement au Registre, le fichier .ini de l'application, ou sous forme binaire dans le cadre de le contenu d'un objet d' `CArchive` .  
  
 La barre peut être une barre de contrôles ancrable, y compris une barre d'outils, une barre d'état, ou une barre de boîte de dialogue.  Les objets d'`CDockState` sont écrits et lisent à partir d'un fichier via un objet d' `CArchive` .  
  
 [CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md) extrait les informations d'état d' `CControlBar` de l'ensemble de la fenêtre frame l'objet et place dans l'objet de `CDockState` .  Vous pouvez ensuite écrire le contenu de l'objet d' `CDockState` à la mémoire avec [sérialisez](../Topic/CObject::Serialize.md) ou [CDockState::SaveState](../Topic/CDockState::SaveState.md).  Si vous souhaitez ultérieurement restaurer l'état des barres de contrôles dans la fenêtre frame, vous pouvez charger l'état et `Serialize` ou [CDockState::LoadState](../Topic/CDockState::LoadState.md), puis utilisez [CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md) pour appliquer l'état enregistré aux barres de contrôles de la fenêtre frame.  
  
 Pour plus d'informations sur l'ancrage des barres de contrôles, consultez les articles [barres de contrôles](../../mfc/control-bars.md), [barres d'outils : L'ancrage et flottant](../../mfc/docking-and-floating-toolbars.md), et [fenêtres frames](../../mfc/frame-windows.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## Configuration requise  
 **Header:** afxadv.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)