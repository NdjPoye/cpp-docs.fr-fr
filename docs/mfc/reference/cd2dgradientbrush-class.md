---
title: "Classe CD2DGradientBrush | Microsoft Docs"
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
  - "CD2DGradientBrush"
  - "afxrendertarget/CD2DGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGradientBrush (classe)"
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DGradientBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe de base des classes CD2DLinearGradientBrush et CD2DRadialGradientBrush.  
  
## Syntaxe  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](../Topic/CD2DGradientBrush::CD2DGradientBrush.md)|Construit un objet CD2DGradientBrush.|  
|[CD2DGradientBrush::~CD2DGradientBrush](../Topic/CD2DGradientBrush::~CD2DGradientBrush.md)|Le destructeur.  Appelé lorsqu'un objet brush de dégradé D2D est détruit.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md)|Détruit un objet CD2DGradientBrush.  \(Substitue [CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md).\)|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGradientBrush::m\_arGradientStops](../Topic/CD2DGradientBrush::m_arGradientStops.md)|Tableau des structures D2D1\_GRADIENT\_STOP.|  
|[CD2DGradientBrush::m\_colorInterpolationGamma](../Topic/CD2DGradientBrush::m_colorInterpolationGamma.md)|Espace dans lequel est exécutée l'interpolation chromatique entre les points de dégradé.|  
|[CD2DGradientBrush::m\_extendMode](../Topic/CD2DGradientBrush::m_extendMode.md)|Comportement du dégradé à l'extérieur de la plage \[0,1\] normalisée.|  
|[CD2DGradientBrush::m\_pGradientStops](../Topic/CD2DGradientBrush::m_pGradientStops.md)|Pointeur vers un tableau de structures D2D1\_GRADIENT\_STOP.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)