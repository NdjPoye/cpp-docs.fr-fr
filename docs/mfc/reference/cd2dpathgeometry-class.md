---
title: "Classe CD2DPathGeometry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DPathGeometry"
  - "CD2DPathGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DPathGeometry (classe)"
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CD2DPathGeometry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1PathGeometry.  
  
## Syntaxe  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](../Topic/CD2DPathGeometry::CD2DPathGeometry.md)|Construit un objet CD2DPathGeometry.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DPathGeometry::Attach](../Topic/CD2DPathGeometry::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DPathGeometry::Create](../Topic/CD2DPathGeometry::Create.md)|Crée CD2DPathGeometry.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DPathGeometry::Destroy](../Topic/CD2DPathGeometry::Destroy.md)|Détruit un objet CD2DPathGeometry.  \(Substitue [CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md).\)|  
|[CD2DPathGeometry::Detach](../Topic/CD2DPathGeometry::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DPathGeometry::GetFigureCount](../Topic/CD2DPathGeometry::GetFigureCount.md)|Extrait nombre de figures dans la géométrie de tracé.|  
|[CD2DPathGeometry::GetSegmentCount](../Topic/CD2DPathGeometry::GetSegmentCount.md)|Extrait le nombre de segments dans la géométrie de tracé.|  
|[CD2DPathGeometry::Open](../Topic/CD2DPathGeometry::Open.md)|Extrait le récepteur de la géométrie qui est utilisé pour remplir la géométrie de tracé avec les figures et les segments.|  
|[CD2DPathGeometry::Stream](../Topic/CD2DPathGeometry::Stream.md)|Copie le contenu de la géométrie de tracé vers l'objet ID2D1GeometrySink spécifié.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DPathGeometry::m\_pPathGeometry](../Topic/CD2DPathGeometry::m_pPathGeometry.md)|Pointeur vers un ID2D1PathGeometry.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 [CD2DPathGeometry](../../mfc/reference/cd2dpathgeometry-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)