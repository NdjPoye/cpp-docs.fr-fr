---
title: "Classe CD2DGeometry | Microsoft Docs"
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
  - "CD2DGeometry"
  - "afxrendertarget/CD2DGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometry (classe)"
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DGeometry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1Geometry.  
  
## Syntaxe  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometry::CD2DGeometry](../Topic/CD2DGeometry::CD2DGeometry.md)|Construit un objet CD2DGeometry.|  
|[CD2DGeometry::~CD2DGeometry](../Topic/CD2DGeometry::~CD2DGeometry.md)|Le destructeur.  Appelé lorsqu'un objet de géométrie D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometry::Attach](../Topic/CD2DGeometry::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DGeometry::CombineWithGeometry](../Topic/CD2DGeometry::CombineWithGeometry.md)|Combine cette géométrie avec la géométrie spécifiée et stocke le résultat dans un ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](../Topic/CD2DGeometry::CompareWithGeometry.md)|Décrit l'intersection entre cette géométrie et la géométrie spécifiée.  La comparaison est exécutée à l'aide de la tolérance d'aplatissement spécifiée.|  
|[CD2DGeometry::ComputeArea](../Topic/CD2DGeometry::ComputeArea.md)|Calcule la zone de la géométrie après sa transformation par la matrice spécifiée et son aplatissement à l'aide de la tolérance spécifiée.|  
|[CD2DGeometry::ComputeLength](../Topic/CD2DGeometry::ComputeLength.md)|Calcule la longueur de la géométrie comme si chaque segment était déroulé dans une ligne.|  
|[CD2DGeometry::ComputePointAtLength](../Topic/CD2DGeometry::ComputePointAtLength.md)|Calcule le point et le vecteur de la tangente à la distance spécifiée le long de la géométrie après sa transformation par la matrice spécifiée et aplati à l'aide de la tolérance spécifiée.|  
|[CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md)|Détruit un objet CD2DGeometry.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DGeometry::Detach](../Topic/CD2DGeometry::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DGeometry::FillContainsPoint](../Topic/CD2DGeometry::FillContainsPoint.md)|Indique si la zone rempli par la géométrie contient le point spécifié selon la tolérance de l'aplatissement spécifiée.|  
|[CD2DGeometry::Get](../Topic/CD2DGeometry::Get.md)|Renvoie l'interface ID2D1Geometry|  
|[CD2DGeometry::GetBounds](../Topic/CD2DGeometry::GetBounds.md)||  
|[CD2DGeometry::GetWidenedBounds](../Topic/CD2DGeometry::GetWidenedBounds.md)|Obtient les limites de la géométrie après son élargissement par la largeur du trait et style spécifiés et après sa transformation par la matrice spécifiée.|  
|[CD2DGeometry::IsValid](../Topic/CD2DGeometry::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DGeometry::Outline](../Topic/CD2DGeometry::Outline.md)|Calcule le plan de la géométrie et enregistre le résultat dans un ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](../Topic/CD2DGeometry::Simplify.md)|Crée une version simplifiée de la géométrie que contient uniquement des lignes et \(éventuellement\) des courbes de Bézier cubiques, puis écrit le résultat dans un objet ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::StrokeContainsPoint](../Topic/CD2DGeometry::StrokeContainsPoint.md)|Détermine si le trait de la géométrie contient le point spécifié en fonction de l'épaisseur du trait, du style et de la transformation spécifiés.|  
|[CD2DGeometry::Tessellate](../Topic/CD2DGeometry::Tessellate.md)|Crée un ensemble de triangles enroulés dans le sens des aiguilles d'une montre qui couvrent la géométrie après sa transformation à l'aide de la matrice spécifiée et son aplatissement à l'aide de la tolérance spécifiée.|  
|[CD2DGeometry::Widen](../Topic/CD2DGeometry::Widen.md)|Élargit la géométrie par le trait spécifié et écrit le résultat dans ID2D1SimplifiedGeometrySink après sa transformation par la matrice spécifiée et son aplatissement à l'aide de la tolérance spécifiée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry\*](../Topic/CD2DGeometry::operator%20ID2D1Geometry*.md)|Renvoie l'interface ID2D1Geometry|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometry::m\_pGeometry](../Topic/CD2DGeometry::m_pGeometry.md)|Pointeur vers un ID2D1Geometry.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)