---
title: "CProgressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl class"
  - "Internet Explorer 4.0 common controls"
  - "progress controls [C++], CProgressCtrl class"
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CProgressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle de barre de progression communs windows.  
  
## Syntaxe  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CProgressCtrl::CProgressCtrl](../Topic/CProgressCtrl::CProgressCtrl.md)|Construit un objet `CProgressCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)|Crée un contrôle de barre de progression et l'attache à un objet d' `CProgressCtrl` .|  
|[CProgressCtrl::CreateEx](../Topic/CProgressCtrl::CreateEx.md)|Crée un contrôle de progression avec les styles étendus par windows spécifiées et l'attache à un objet d' `CProgressCtrl` .|  
|[CProgressCtrl::GetBarColor](../Topic/CProgressCtrl::GetBarColor.md)|Obtient la couleur de la barre d'indicateur de progression pour le contrôle de barre de progression actuel.|  
|[CProgressCtrl::GetBkColor](../Topic/CProgressCtrl::GetBkColor.md)|Obtient la couleur d'arrière\-plan actuelle de la barre de progression.|  
|[CProgressCtrl::GetPos](../Topic/CProgressCtrl::GetPos.md)|Obtient la position actuelle de la barre de progression.|  
|[CProgressCtrl::GetRange](../Topic/CProgressCtrl::GetRange.md)|Obtient les limites inférieures et supérieures de la plage du contrôle de barre de progression.|  
|[CProgressCtrl::GetState](../Topic/CProgressCtrl::GetState.md)|Obtient l'état du contrôle de barre de progression actuel.|  
|[CProgressCtrl::GetStep](../Topic/CProgressCtrl::GetStep.md)|Récupère l'index d'étape pour la barre de progression du contrôle de barre de progression actuel.|  
|[CProgressCtrl::OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)|Avance la position actuelle d'un contrôle de barre de progression d'un index spécifié et redessine la barre pour refléter la nouvelle position.|  
|[CProgressCtrl::SetBarColor](../Topic/CProgressCtrl::SetBarColor.md)|Définit la couleur de la barre d'indicateur de progression dans le contrôle de barre de progression actuel.|  
|[CProgressCtrl::SetBkColor](../Topic/CProgressCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan pour la barre de progression.|  
|[CProgressCtrl::SetMarquee](../Topic/CProgressCtrl::SetMarquee.md)|Active ou désactive le mode de bannière désactiver pour le contrôle de barre de progression actuel.|  
|[CProgressCtrl::SetPos](../Topic/CProgressCtrl::SetPos.md)|Définit la position actuelle pour un contrôle de barre de progression et redessine la barre pour refléter la nouvelle position.|  
|[CProgressCtrl::SetRange](../Topic/CProgressCtrl::SetRange.md)|Définit le minimum et les portées maximales pour un contrôle de barre de progression et redessine la barre pour refléter les nouvelles gammes.|  
|[CProgressCtrl::SetState](../Topic/CProgressCtrl::SetState.md)|Définit l'état du contrôle de barre de progression actuel.|  
|[CProgressCtrl::SetStep](../Topic/CProgressCtrl::SetStep.md)|Spécifie l'index de l'étape pour un contrôle de barre de progression.|  
|[CProgressCtrl::StepIt](../Topic/CProgressCtrl::StepIt.md)|Avance la position actuelle pour un contrôle de barre de progression par l'index de l'étape \(consultez [SetStep](../Topic/CProgressCtrl::SetStep.md)\) et redessine la barre pour refléter la nouvelle position.|  
  
## Notes  
 Un contrôle de barre de progression est une fenêtre qu'une application peut utiliser pour indiquer la progression d'une longue opération.  Il se compose d'un rectangle qui est progressivement rempli, de gauche à droite, avec la couleur de surbrillance système comme une opération progresse.  
  
 Un contrôle de barre de progression est une plage et une position actuelle.  L'intervalle représente la durée totale de l'exécution, et la position actuelle représente la progression de l'application est réalisée dans l'achèvement de l'exécution.  La procédure de fenêtre utilise l'intervalle et la position actuelle pour déterminer le pourcentage de la barre de progression pour remplir de couleur de surbrillance.  Étant donné que les valeurs de plage et de position actuelle sont exprimées comme un entier signé, l'intervalle possible des valeurs de position actuelle est \(de 2.147.483.648 à 2.147.483.647 inclus.  
  
 Pour plus d'informations sur l'utilisation `CProgressCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## Configuration requise  
 **en\-tête :** afxcmn.h  
  
## Voir aussi  
 [MFC exemple CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)