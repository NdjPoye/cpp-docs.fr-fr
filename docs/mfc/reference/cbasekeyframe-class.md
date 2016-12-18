---
title: "Classe CBaseKeyFrame | Microsoft Docs"
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
  - "CBaseKeyFrame"
  - "afxanimationcontroller/CBaseKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseKeyFrame (classe)"
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CBaseKeyFrame
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités de base d'une image clé.  
  
## Syntaxe  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](../Topic/CBaseKeyFrame::CBaseKeyFrame.md)|Construit un objet image clé.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md)|Ajoute une image clé au storyboard.|  
|[CBaseKeyFrame::GetAnimationKeyframe](../Topic/CBaseKeyFrame::GetAnimationKeyframe.md)|Retourne la valeur de l'image clé sous\-jacente.|  
|[CBaseKeyFrame::IsAdded](../Topic/CBaseKeyFrame::IsAdded.md)|Indique si une image clé a été ajoutée au storyboard.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](../Topic/CBaseKeyFrame::IsKeyframeAtOffset.md)|Indique si l'image clé doit être ajoutée au storyboard à l'offset, ou après la transition.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseKeyFrame::m\_bAdded](../Topic/CBaseKeyFrame::m_bAdded.md)|Spécifie si cette image clé a été ajoutée à un storyboard.|  
|[CBaseKeyFrame::m\_bIsKeyframeAtOffset](../Topic/CBaseKeyFrame::m_bIsKeyframeAtOffset.md)|Indique si ces images clés doivent être ajoutées au storyboard à un offset à partir d'une autre image clé existante ou à la fin d'une transition.|  
|[CBaseKeyFrame::m\_keyframe](../Topic/CBaseKeyFrame::m_keyframe.md)|Représente une image clé de l'API Animation Windows.  Lorsqu'une image clé n'est pas initialisée, elle a la valeur prédéfinie UI\_ANIMATION\_KEYFRAME\_STORYBOARD\_START.|  
  
## Notes  
 Encapsule la variable UI\_ANIMATION\_KEYFRAME.  Sert de classe de base pour les implémentations des images clés.  Une image clé représente un moment dans le temps dans un storyboard et peut être utilisée pour spécifier les heures de début et de fin des transitions.  Il existe deux types d'images clés : images clés ajoutées au storyboard à l'offset spécifié \(à un moment donné\) ou images clés ajoutées après la transition spécifiée.  Comme les durées de certaines transitions ne peuvent pas être connues avant le démarrage de l'animation, les valeurs réelles de certaines images clés sont déterminées au moment de l'exécution uniquement.  Comme les images clés peuvent dépendre des transitions, qui à leur tour dépendent des images clés, il est important d'éviter les récurrences infinies lors de la génération des chaînes d'images clés.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)