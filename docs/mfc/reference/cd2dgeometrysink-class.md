---
title: "Classe CD2DGeometrySink | Microsoft Docs"
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
  - "afxrendertarget/CD2DGeometrySink"
  - "CD2DGeometrySink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometrySink (classe)"
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DGeometrySink
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1GeometrySink.  
  
## Syntaxe  
  
```  
class CD2DGeometrySink;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](../Topic/CD2DGeometrySink::CD2DGeometrySink.md)|Construit un objet CD2DGeometrySink à partir de l'objet CD2DPathGeometry.|  
|[CD2DGeometrySink::~CD2DGeometrySink](../Topic/CD2DGeometrySink::~CD2DGeometrySink.md)|Le destructeur.  Appelé lorsqu'un récepteur de géométrie D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometrySink::AddArc](../Topic/CD2DGeometrySink::AddArc.md)|Ajoute un arc unique à la géométrie de tracé|  
|[CD2DGeometrySink::AddBezier](../Topic/CD2DGeometrySink::AddBezier.md)|Crée une courbe de Bézier cubique entre le point actuel et le point de terminaison spécifié.|  
|[CD2DGeometrySink::AddBeziers](../Topic/CD2DGeometrySink::AddBeziers.md)|Crée une séquence de courbes de Bézier cubiques et les ajoute au récepteur de la géométrie.|  
|[CD2DGeometrySink::AddLine](../Topic/CD2DGeometrySink::AddLine.md)|Crée un segment de ligne entre le point actuel et le point de terminaison spécifié, puis l'ajoute au récepteur de la géométrie.|  
|[CD2DGeometrySink::AddLines](../Topic/CD2DGeometrySink::AddLines.md)|Crée une séquence de lignes à l'aide des points spécifiés et les ajoute au récepteur de la géométrie.|  
|[CD2DGeometrySink::AddQuadraticBezier](../Topic/CD2DGeometrySink::AddQuadraticBezier.md)|Crée une courbe de Bézier quadratique entre le point actuel et le point de terminaison spécifié.|  
|[CD2DGeometrySink::AddQuadraticBeziers](../Topic/CD2DGeometrySink::AddQuadraticBeziers.md)|Ajoute une séquence de segments quadratiques de Bézier sous la forme d'un tableau dans un seul appel.|  
|[CD2DGeometrySink::BeginFigure](../Topic/CD2DGeometrySink::BeginFigure.md)|Démarre une nouvelle figure au point spécifié.|  
|[CD2DGeometrySink::Close](../Topic/CD2DGeometrySink::Close.md)|Ferme le récepteur de la géométrie|  
|[CD2DGeometrySink::EndFigure](../Topic/CD2DGeometrySink::EndFigure.md)|Termine la figure en cours et la ferme éventuellement.|  
|[CD2DGeometrySink::Get](../Topic/CD2DGeometrySink::Get.md)|Renvoie l'interface ID2D1GeometrySink|  
|[CD2DGeometrySink::IsValid](../Topic/CD2DGeometrySink::IsValid.md)|Vérifie la validité du récepteur de la géométrie|  
|[CD2DGeometrySink::SetFillMode](../Topic/CD2DGeometrySink::SetFillMode.md)|Spécifie la méthode utilisée pour déterminer les points situés à l'intérieur de la géométrie décrite par ce récepteur de la géométrie et les points situés à l'extérieur.|  
|[CD2DGeometrySink::SetSegmentFlags](../Topic/CD2DGeometrySink::SetSegmentFlags.md)|Spécifie les options de trait et de jointure à appliquer aux nouveaux segments ajoutés au récepteur de la géométrie.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink\*](../Topic/CD2DGeometrySink::operator%20ID2D1GeometrySink*.md)|Renvoie l'interface ID2D1GeometrySink|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DGeometrySink::m\_pSink](../Topic/CD2DGeometrySink::m_pSink.md)|Pointeur vers un ID2D1GeometrySink.|  
  
## Hiérarchie d'héritage  
 [CD2DGeometrySink](../../mfc/reference/cd2dgeometrysink-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)