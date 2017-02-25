---
title: "CSliderCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl class"
  - "CSliderCtrl class, contrôles communs"
  - "contrôles Slider, CSliderCtrl class"
  - "Windows common controls [C++], CSliderCtrl"
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSliderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle Slider communs windows.  
  
## Syntaxe  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSliderCtrl::CSliderCtrl](../Topic/CSliderCtrl::CSliderCtrl.md)|Construit un objet `CSliderCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSliderCtrl::ClearSel](../Topic/CSliderCtrl::ClearSel.md)|Efface la sélection actuelle dans un contrôle Slider.|  
|[CSliderCtrl::ClearTics](../Topic/CSliderCtrl::ClearTics.md)|Supprime les graduations actuelles d'un contrôle Slider.|  
|[CSliderCtrl::Create](../Topic/CSliderCtrl::Create.md)|Crée un contrôle Slider et l'attache à un objet d' `CSliderCtrl` .|  
|[CSliderCtrl::CreateEx](../Topic/CSliderCtrl::CreateEx.md)|Crée un contrôle Slider avec les styles étendus par windows spécifiées et l'attache à un objet d' `CSliderCtrl` .|  
|[CSliderCtrl::GetBuddy](../Topic/CSliderCtrl::GetBuddy.md)|Récupère le handle vers une fenêtre associé de contrôle Slider à un emplacement donné.|  
|[CSliderCtrl::GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md)|Extrait la taille du canal du contrôle Slider.|  
|[CSliderCtrl::GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)|Extrait la taille de ligne d'un contrôle Slider.|  
|[CSliderCtrl::GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)|Récupère le nombre de graduations dans un contrôle Slider.|  
|[CSliderCtrl::GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)|Extrait la Taille de page d'un contrôle Slider.|  
|[CSliderCtrl::GetPos](../Topic/CSliderCtrl::GetPos.md)|Extrait du curseur.|  
|[CSliderCtrl::GetRange](../Topic/CSliderCtrl::GetRange.md)|Récupère les positions de minimale et maximale de pour un curseur.|  
|[CSliderCtrl::GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)|Extrait la position maximale pour un curseur.|  
|[CSliderCtrl::GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)|Extrait la position minimale pour un curseur.|  
|[CSliderCtrl::GetSelection](../Topic/CSliderCtrl::GetSelection.md)|Récupère l'intervalle de la sélection actuelle.|  
|[CSliderCtrl::GetThumbLength](../Topic/CSliderCtrl::GetThumbLength.md)|Extrait la longueur du curseur dans le contrôle TrackBar actuel.|  
|[CSliderCtrl::GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md)|Extrait la taille de curseur de défilement du contrôle Slider.|  
|[CSliderCtrl::GetTic](../Topic/CSliderCtrl::GetTic.md)|Extrait la position de la graduation spécifiée.|  
|[CSliderCtrl::GetTicArray](../Topic/CSliderCtrl::GetTicArray.md)|Récupère le tableau de positions de graduation pour un contrôle Slider.|  
|[CSliderCtrl::GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)|Extrait la position de la graduation spécifiée, dans les coordonnées clientes.|  
|[CSliderCtrl::GetToolTips](../Topic/CSliderCtrl::GetToolTips.md)|Récupère le handle au contrôle d'info\-bulle assigné au contrôle Slider échéant.|  
|[CSliderCtrl::SetBuddy](../Topic/CSliderCtrl::SetBuddy.md)|Assigne une fenêtre comme fenêtre associé à un contrôle Slider.|  
|[CSliderCtrl::SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)|Définit la taille de ligne d'un contrôle Slider.|  
|[CSliderCtrl::SetPageSize](../Topic/CSliderCtrl::SetPageSize.md)|Définit la Taille de page d'un contrôle Slider.|  
|[CSliderCtrl::SetPos](../Topic/CSliderCtrl::SetPos.md)|Définit la position actuelle du curseur.|  
|[CSliderCtrl::SetRange](../Topic/CSliderCtrl::SetRange.md)|Définit les positions de minimale et maximale de pour un curseur.|  
|[CSliderCtrl::SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md)|Définit la position maximale pour un curseur.|  
|[CSliderCtrl::SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md)|Définit la position minimale pour un curseur.|  
|[CSliderCtrl::SetSelection](../Topic/CSliderCtrl::SetSelection.md)|Définit l'intervalle de la sélection actuelle.|  
|[CSliderCtrl::SetThumbLength](../Topic/CSliderCtrl::SetThumbLength.md)|Définit la longueur du curseur dans le contrôle TrackBar actuel.|  
|[CSliderCtrl::SetTic](../Topic/CSliderCtrl::SetTic.md)|Définit la position de la graduation spécifiée.|  
|[CSliderCtrl::SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md)|Définit la fréquence des graduations par index de contrôle Slider.|  
|[CSliderCtrl::SetTipSide](../Topic/CSliderCtrl::SetTipSide.md)|Positionne un contrôle d'info\-bulle utilisé par un contrôle TrackBar.|  
|[CSliderCtrl::SetToolTips](../Topic/CSliderCtrl::SetToolTips.md)|Assigne un contrôle d'info\-bulle à un contrôle Slider.|  
  
## Notes  
 Un « contrôle Slider » \(également appelé trackbar\) est une fenêtre contenant un curseur et des graduations facultatives.  Lorsque l'utilisateur déplace le curseur, à l'aide de la souris ou les touches de direction, le contrôle envoie des messages de notification pour indiquer la modification.  
  
 Les contrôles Slider sont utiles lorsque vous souhaitez l'utilisateur de sélectionner une valeur discrète ou un ensemble de valeurs consécutives à une plage.  Par exemple, vous pouvez utiliser un contrôle Slider pour permettre à l'utilisateur de définir le taux de répétition du clavier en déplaçant le curseur d'une graduation donnée.  
  
 Ce contrôle \(et par conséquent la classe d' `CSliderCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Le curseur se déplace dans les index que vous spécifiez lorsque vous les créez.  Par exemple, si vous spécifiez que le curseur doit avoir une plage de cinq, le curseur ne peut occuper six positions : une position à gauche du contrôle Slider et une position pour chaque index dans la plage.  En général, chacune de ces emplacements est identifiée par une graduation.  
  
 Vous créez un curseur en utilisant le constructeur et la fonction membre de **Créer** d' `CSliderCtrl`.  Une fois que vous avez créé un contrôle Slider, vous pouvez utiliser des fonctions membres dans `CSliderCtrl` pour modifier plusieurs de ses propriétés.  Les modifications que vous pouvez effectuer inclure définir les positions de minimale et maximale de pour le curseur, les graduations de dessin, la définition d'une plage de sélection, et le repositionnement du curseur.  
  
 Pour plus d'informations sur l'utilisation `CSliderCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl Class](../../mfc/reference/cprogressctrl-class.md)