---
title: "Classe CD2DBrush | Microsoft Docs"
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
  - "CD2DBrush"
  - "afxrendertarget/CD2DBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBrush (classe)"
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1Brush.  
  
## Syntaxe  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBrush::CD2DBrush](../Topic/CD2DBrush::CD2DBrush.md)|Construit un objet CD2DBrush.|  
|[CD2DBrush::~CD2DBrush](../Topic/CD2DBrush::~CD2DBrush.md)|Le destructeur.  Appelé lorsqu'un objet brush D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBrush::Attach](../Topic/CD2DBrush::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md)|Détruit un objet CD2DBrush.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBrush::Detach](../Topic/CD2DBrush::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DBrush::Get](../Topic/CD2DBrush::Get.md)|Renvoie l'interface ID2D1Brush|  
|[CD2DBrush::GetOpacity](../Topic/CD2DBrush::GetOpacity.md)|Obtient le degré d'opacité de ce pinceau|  
|[CD2DBrush::GetTransform](../Topic/CD2DBrush::GetTransform.md)|Obtient la transformation en cours de la cible de rendu.|  
|[CD2DBrush::IsValid](../Topic/CD2DBrush::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DBrush::SetOpacity](../Topic/CD2DBrush::SetOpacity.md)|Définit le degré d'opacité de ce pinceau|  
|[CD2DBrush::SetTransform](../Topic/CD2DBrush::SetTransform.md)|Applique la transformation spécifiée à la cible de rendu remplaçant la transformation existante.  Toutes les opérations de dessin suivantes se produisent dans l'espace transformé|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBrush::operator ID2D1Brush\*](../Topic/CD2DBrush::operator%20ID2D1Brush*.md)|Renvoie l'interface ID2D1Brush|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBrush::m\_pBrush](../Topic/CD2DBrush::m_pBrush.md)|Stocke un pointeur à un objet ID2D1Brush.|  
|[CD2DBrush::m\_pBrushProperties](../Topic/CD2DBrush::m_pBrushProperties.md)|Propriétés des pinceaux.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)