---
title: "Classe CD2DLinearGradientBrush | Microsoft Docs"
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
  - "afxrendertarget/CD2DLinearGradientBrush"
  - "CD2DLinearGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLinearGradientBrush (classe)"
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DLinearGradientBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1LinearGradientBrush.  
  
## Syntaxe  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](../Topic/CD2DLinearGradientBrush::CD2DLinearGradientBrush.md)|Construit un objet CD2DLinearGradientBrush.|  
|[CD2DLinearGradientBrush::~CD2DLinearGradientBrush](../Topic/CD2DLinearGradientBrush::~CD2DLinearGradientBrush.md)|Le destructeur.  Appelé lorsqu'un objet brush de dégradé linéaire D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLinearGradientBrush::Attach](../Topic/CD2DLinearGradientBrush::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DLinearGradientBrush::Create](../Topic/CD2DLinearGradientBrush::Create.md)|Crée CD2DLinearGradientBrush.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DLinearGradientBrush::Destroy](../Topic/CD2DLinearGradientBrush::Destroy.md)|Détruit un objet CD2DLinearGradientBrush.  \(Substitue [CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md).\)|  
|[CD2DLinearGradientBrush::Detach](../Topic/CD2DLinearGradientBrush::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DLinearGradientBrush::Get](../Topic/CD2DLinearGradientBrush::Get.md)|Renvoie l'interface ID2D1LinearGradientBrush|  
|[CD2DLinearGradientBrush::GetEndPoint](../Topic/CD2DLinearGradientBrush::GetEndPoint.md)|Extrait les coordonnées de fin du dégradé linéaire|  
|[CD2DLinearGradientBrush::GetStartPoint](../Topic/CD2DLinearGradientBrush::GetStartPoint.md)|Extrait les coordonnées de début du dégradé linéaire|  
|[CD2DLinearGradientBrush::SetEndPoint](../Topic/CD2DLinearGradientBrush::SetEndPoint.md)|Définit les coordonnées de fin du dégradé linéaire dans l'espace des coordonnées du pinceau|  
|[CD2DLinearGradientBrush::SetStartPoint](../Topic/CD2DLinearGradientBrush::SetStartPoint.md)|Définit les coordonnées de début du dégradé linéaire dans l'espace des coordonnées du pinceau|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush\*](../Topic/CD2DLinearGradientBrush::operator%20ID2D1LinearGradientBrush*.md)|Renvoie l'interface ID2D1LinearGradientBrush|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLinearGradientBrush::m\_LinearGradientBrushProperties](../Topic/CD2DLinearGradientBrush::m_LinearGradientBrushProperties.md)|Points de début et de fin du dégradé.|  
|[CD2DLinearGradientBrush::m\_pLinearGradientBrush](../Topic/CD2DLinearGradientBrush::m_pLinearGradientBrush.md)|Pointeur vers un ID2D1LinearGradientBrush.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 [CD2DLinearGradientBrush](../../mfc/reference/cd2dlineargradientbrush-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)