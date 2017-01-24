---
title: "Classe CD2DMesh | Microsoft Docs"
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
  - "afxrendertarget/CD2DMesh"
  - "CD2DMesh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DMesh (classe)"
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DMesh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1Mesh.  
  
## Syntaxe  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DMesh::CD2DMesh](../Topic/CD2DMesh::CD2DMesh.md)|Construit un objet CD2DMesh.|  
|[CD2DMesh::~CD2DMesh](../Topic/CD2DMesh::~CD2DMesh.md)|Le destructeur.  Appelé lorsqu'un objet maillage D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DMesh::Attach](../Topic/CD2DMesh::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DMesh::Create](../Topic/CD2DMesh::Create.md)|Crée CD2DMesh.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DMesh::Destroy](../Topic/CD2DMesh::Destroy.md)|Détruit un objet CD2DMesh.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DMesh::Detach](../Topic/CD2DMesh::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DMesh::Get](../Topic/CD2DMesh::Get.md)|Renvoie l'interface ID2D1Mesh|  
|[CD2DMesh::IsValid](../Topic/CD2DMesh::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DMesh::Open](../Topic/CD2DMesh::Open.md)|Ouvre le maillage pour le remplissage.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DMesh::operator ID2D1Mesh\*](../Topic/CD2DMesh::operator%20ID2D1Mesh*.md)|Renvoie l'interface ID2D1Mesh|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DMesh::m\_pMesh](../Topic/CD2DMesh::m_pMesh.md)|Pointeur vers un ID2D1Mesh.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DMesh](../../mfc/reference/cd2dmesh-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)