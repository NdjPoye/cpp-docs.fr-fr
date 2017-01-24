---
title: "Classe CD2DLayer | Microsoft Docs"
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
  - "afxrendertarget/CD2DLayer"
  - "CD2DLayer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLayer (classe)"
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DLayer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1Layer.  
  
## Syntaxe  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLayer::CD2DLayer](../Topic/CD2DLayer::CD2DLayer.md)|Construit un objet CD2DLayer.|  
|[CD2DLayer::~CD2DLayer](../Topic/CD2DLayer::~CD2DLayer.md)|Le destructeur.  Appelé lorsqu'un objet couche D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLayer::Attach](../Topic/CD2DLayer::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DLayer::Create](../Topic/CD2DLayer::Create.md)|Crée CD2DLayer.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DLayer::Destroy](../Topic/CD2DLayer::Destroy.md)|Détruit un objet CD2DLayer.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DLayer::Detach](../Topic/CD2DLayer::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DLayer::Get](../Topic/CD2DLayer::Get.md)|Renvoie l'interface ID2D1Layer|  
|[CD2DLayer::GetSize](../Topic/CD2DLayer::GetSize.md)|Renvoie la taille de la cible de rendu en DIP|  
|[CD2DLayer::IsValid](../Topic/CD2DLayer::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLayer::operator ID2D1Layer\*](../Topic/CD2DLayer::operator%20ID2D1Layer*.md)|Renvoie l'interface ID2D1Layer|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DLayer::m\_pLayer](../Topic/CD2DLayer::m_pLayer.md)|Stocke un pointeur à un objet ID2D1Layer.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DLayer](../../mfc/reference/cd2dlayer-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)