---
title: "CSpinButtonCtrl Class | Microsoft Docs"
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
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl class"
  - "CSpinButtonCtrl class, contrôles communs"
  - "contrôle toupie"
  - "contrôles up-down, contrôle toupie"
  - "Windows common controls [C++], CSpinButtonCtrl"
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle toupie communs windows.  
  
## Syntaxe  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](../Topic/CSpinButtonCtrl::CSpinButtonCtrl.md)|Construit un objet `CSpinButtonCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSpinButtonCtrl::Create](../Topic/CSpinButtonCtrl::Create.md)|Crée un contrôle toupie et l'attache à un objet d' `CSpinButtonCtrl` .|  
|[CSpinButtonCtrl::CreateEx](../Topic/CSpinButtonCtrl::CreateEx.md)|Crée un contrôle toupie avec les styles étendus par windows spécifiées et l'attache à un objet d' `CSpinButtonCtrl` .|  
|[CSpinButtonCtrl::GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)|Récupère les informations d'accélération pour un contrôle toupie.|  
|[CSpinButtonCtrl::GetBase](../Topic/CSpinButtonCtrl::GetBase.md)|Extrait la base actuelle d'un contrôle toupie.|  
|[CSpinButtonCtrl::GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md)|Extrait un pointeur vers la fenêtre associé actuelle.|  
|[CSpinButtonCtrl::GetPos](../Topic/CSpinButtonCtrl::GetPos.md)|Extrait la position actuelle d'un contrôle toupie.|  
|[CSpinButtonCtrl::GetRange](../Topic/CSpinButtonCtrl::GetRange.md)|Extrait la limite supérieure et les limites inférieures \(plage\) pour un contrôle toupie.|  
|[CSpinButtonCtrl::SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md)|Définit l'accélération pour un contrôle toupie.|  
|[CSpinButtonCtrl::SetBase](../Topic/CSpinButtonCtrl::SetBase.md)|Définit la base pour un contrôle toupie.|  
|[CSpinButtonCtrl::SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)|Définit la fenêtre associé à un contrôle toupie.|  
|[CSpinButtonCtrl::SetPos](../Topic/CSpinButtonCtrl::SetPos.md)|Définit la position actuelle pour le contrôle.|  
|[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)|Définit la limite supérieure et les limites inférieures \(plage\) pour un contrôle toupie.|  
  
## Notes  
 Un « contrôle » toupie \(également appelé un contrôle up\-down\) est une paire de boutons fléchés que l'utilisateur peut cliquer pour incrémenter ou décrémenter une valeur, telle qu'une position de défilement ou un nombre affiché dans un contrôle auxiliaires.  La valeur associée à un contrôle toupie est appelée sa position actuelle.  Un contrôle toupie est le plus souvent utilisé avec un contrôle auxiliaires, appelé une « fenêtre associé. »  
  
 Ce contrôle \(et par conséquent la classe d' `CSpinButtonCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 À l'utilisateur, à un contrôle toupie et son de fenêtre associé se présenter souvent à un seul contrôle.  Vous pouvez spécifier qu'un contrôle toupie se positionnent automatiquement en regard de sa fenêtre associé, et qu'il a automatiquement la légende de la fenêtre associé à sa position actuelle.  Vous pouvez utiliser un contrôle toupie avec un contrôle d'édition pour inviter l'utilisateur à l'entrée numérique.  
  
 Cliquez sur la flèche haut déplace la position actuelle vers le maximum, puis cliquez sur la flèche bas déplace la position actuelle vers le minimum.  Par défaut, la valeur minimale est 100 et le nombre maximal est 0.  Lorsque la configuration minimale est supérieure à la valeur maximale \(par exemple, lorsque le paramètre par défaut est utilisée\), cliquez sur la flèche haut diminue la valeur de position et cliquant sur la flèche bas l'augmente.  
  
 Un contrôle toupie sans fonctions de fenêtre associé comme une sorte de barre de défilement simplifiée.  Par exemple, un contrôle onglet affiche parfois un contrôle toupie pour permettre à l'utilisateur de faire défiler les onglets supplémentaires dans la vue.  
  
 Pour plus d'informations sur l'utilisation `CSpinButtonCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)