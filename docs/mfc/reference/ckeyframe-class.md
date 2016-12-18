---
title: "Classe CKeyFrame | Microsoft Docs"
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
  - "afxanimationcontroller/CKeyFrame"
  - "CKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyFrame (classe)"
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CKeyFrame
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une image clé de l'animation.  
  
## Syntaxe  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CKeyFrame::CKeyFrame](../Topic/CKeyFrame::CKeyFrame.md)|Surchargé.  Construit une image clé qui dépend d'une autre image clé.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CKeyFrame::AddToStoryboard](../Topic/CKeyFrame::AddToStoryboard.md)|Ajoute une image clé à un storyboard.  \(Substitue [CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md).\)|  
|[CKeyFrame::AddToStoryboardAfterTransition](../Topic/CKeyFrame::AddToStoryboardAfterTransition.md)|Ajoute une image clé au storyboard après la transition.|  
|[CKeyFrame::AddToStoryboardAtOffset](../Topic/CKeyFrame::AddToStoryboardAtOffset.md)|Ajoute une image clé au storyboard à l'offset.|  
|[CKeyFrame::GetExistingKeyframe](../Topic/CKeyFrame::GetExistingKeyframe.md)|Retourne un pointeur à une image clé dont dépend cette image clé.|  
|[CKeyFrame::GetOffset](../Topic/CKeyFrame::GetOffset.md)|Retourne un offset à partir d'une autre image clé.|  
|[CKeyFrame::GetTransition](../Topic/CKeyFrame::GetTransition.md)|Retourne un pointeur à une transition dont dépend cette image clé.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CKeyFrame::m\_offset](../Topic/CKeyFrame::m_offset.md)|Spécifie l'offset de cet image clé à partir d'une image clé stockée dans m\_pExistingKeyFrame.|  
|[CKeyFrame::m\_pExistingKeyFrame](../Topic/CKeyFrame::m_pExistingKeyFrame.md)|Stocke un pointeur à une image clé existante.  Cette image clé est ajoutée au storyboard avec m\_offset à l'image clé existante.|  
|[CKeyFrame::m\_pTransition](../Topic/CKeyFrame::m_pTransition.md)|Stocke un pointeur à la transtion qui commence à partir de cette image clé.|  
  
## Notes  
 Cette classe implémente une image clé de l'animation.  Une image clé représente un moment dans le temps dans un storyboard et peut être utilisée pour spécifier les heures de début et de fin des transitions.  Une image clé peut être basée sur une autre image clé et présenter un offset \(en secondes\), ou être basée sur une transition et représenter le moment où cette transition se termine.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)